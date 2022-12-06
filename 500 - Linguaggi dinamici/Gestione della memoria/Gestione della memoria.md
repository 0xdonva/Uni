Quando si parla di gestione della memoria, si intende di regola la **gestione dello heap**.
Esistono fondamentalmente due approcci:
- [[Gestione manuale della memoria]]
- [[Gestione automatica della memoria]]

## Allocazione della memoria
Lo **heap** è quella porzione di memoria che può essere acceduta anche al di fuori del contesto di esecuzione in cui è stata allocata.
Un oggetto memorizzato nello heap può essere acceduto mediante *riferimento diretto* oppure tramite una struttura intermedia i cui elementi sono detti *handle*, che a sua volta referenzia l'oggetto.
Il riferimento tramite handle introduce un *extra-overhead* di memoria ma garantisce maggiore efficienza nella *rilocazione* degli oggetti.
Quando il programma effettua una richiesta di memoria il modulo di allocazione *individua* un'opportuna area libera nel *pool* e ne restituisce l'indirizzo, nel caso il pool sia esaurito interverrà il *sistema operativo*.

## Gestione della memoria dell'interprete CPython
L'interazione con il sistema operativo è limitata dall'organizzazione gerarchica adottata da Python:
- *Arene*: il più alto livello, sono porzioni di 256 KB di memoria, tutte le *arene* allocate ad un determinato istante sono collegate fra loro mediante una *lista bidirezionale* (*doubly-linked list*).
- *Pool*: ogni arena è suddivisa in 64 *pool*, ciascuno di dimensione fissa e pari a 4 KB.
- *Blocco*:ogni pool è suddiviso in *blocchi*, la cui dimensione è *fissata all'interno di ogni pool* ma che può essere differente da pool a pool.

### Pool
Un **pool** può trovarsi in tre stati:
1. *In uso*: quando include blocchi allocati ma anche blocchi ancora liberi.
2. *Completo*: quando tutti i blocchi sono allocati.
3. *Vuoto*: quando non ci sono ancora blocchi allocati.

Quando un pool è vuoto, la classe di appartenenza della *prima richiesta* di allocazione determina anche la *classe di allocazione del pool*.

#### Pool in uso
CPython organizza i pool in uso in una struttura a *due livelli*.
La doppia lista serve perché quando un pool si svuota oppure si riempie deve essere "sganciato" e la doppia lista consente di farlo in *tempo costante*.

#### Pool vuoti o completi
I pool vuoti vengono tenuti in una *lista lineare* perché ovviamente in questo caso l'accesso è solo alla testa della lista.
I pool completi non necessitano di essere inseriti in una struttura apposita.

### Blocchi
La dimensione di un blocco può andare da un *minimo di 8 byte* fino ad un *massimo di 512 byte*, una richiesta di $k$ byte si traduce nell'allocazione di $b_k=\lfloor\frac{k-1}{8}\rfloor+1$ byte.
Una tale dimensione di dice di *classe $b_k-1$*.
I blocchi di un pool sono a loro volta partizionati in tre gruppi:
- *In uso*: non sono organizzati in una struttura apposita.
- *Liberi*: sono organizzati in una *lista lineare*.
- *Mai allocati*: occupano uno *spazio contiguo*.

#### Dis-allocazione di un blocco
I casi da analizzare sono tre:
1. Il blocco da dis-allocare è l'unico blocco allocato nel pool;
2. Oltre al blocco da dis-allocare tutti gli altri blocchi sono allocati;
3. Il blocco è da dis-allocare ma ci sono sia blocchi allocati sia liberi.

Pool/arene hanno un *header* che include almeno le seguenti informazioni: numero di blocchi/pool allocati e indirizzo del mio blocco/pool libero.
L'algoritmo è in grado di capire quale caso si applica, si può notare che le dimensioni fisse di arene e pool consentono di determinare l'indirizzo iniziale conoscendo l'indirizzo di un pool o blocco componente.
Il primo passo dell'algoritmo consiste infa