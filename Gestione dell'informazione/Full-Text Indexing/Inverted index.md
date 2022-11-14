Un __indice invertito__ (o __inverted index/file__) e un meccanismo basato sulle parole per indicizzare una collezione di testi in modo tale da velocizzarne la ricerca.
L'[[Index|indice]] invertito è composto da due elementi: il _vocabolario_ e le _occorrenze_.
Il __vocabolario__ è un gruppo di parole tutte diverse tra loro nei testi, per ogni parola esiste una lista delle posizioni in cui appare la parola nei testi.
Il gruppo che contiene tutte queste liste viene detto __occorrenze__.
Queste posizioni possono riferirsi a parole o caratteri.
Le liste di _posizioni di parole_ semplificano le frasi e le query di prossimità, mentre la _posizioni dei caratteri_ facilita l'accesso diretto alla ricerca tramite [[pattern matching]].
Lo spazio richiesto dal _vocabolario_ è _estremamente piccolo_: in base alla _legge di Heaps_, il vocabolario è cresce fino ad un $O(n^{\beta})$, dove $\beta$ è una costante tra $0$ e $1$ che dipende dal testo.
Lo spazio richiesto dalle _occorrenze_ è più grande visto che ogni parola che appare nei testi è inserita in una struttura dati, occuperà circa un $O(n)$.
Questo vuol dire che le _occorrenze_ andranno ad occupare circa il 30/40% della dimensione dei testi.

## Costruzione
Un inverted index di un testo di $n$ caratteri può essere costruito in un tempo $O(n)$.
Tutto il vocabolario fino ad ora conosciuto è contenuto in una struttura dati _trie_, memorizzando per ogni parola un elenco delle sue occorrenze.
Ogni parola viene letta e cercata all'interno del _trie_, se non viene trovata una nuova posizione viene aggiunta in coda alla lista delle occorrenze. Una volta all'interno del trie, la nuova posizione è aggiunta alla fine della lista delle occorrenze.
Una volta che il testo è finito, il trie viene scritto sul disco insieme alla lista delle occorrenze.
È buona norma dividere l'indice in due file: nel primo la lista delle occorrenze è scritta in maniera contigua, nel secondo il vocabolario è salvato in ordine lessicografico e per ogni parola un puntatore alla sua lista nel primo file.

### Complessità
- $O(1)$ operazioni per carattere del testo.
- $O(1)$ per l'inserimento della posizione nella lista delle occorrenze.
- $O(n)$ per gli altri processi.

## Ricerca
Un algoritmo di ricerca di un inverted index segue tre passi generali:
1. _Ricerca nel vocabolario_: le parole e i pattern presenti nelle query vengono isolati e cercati nel vocabolario