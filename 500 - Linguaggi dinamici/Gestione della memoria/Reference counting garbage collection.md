L'idea alla base del **reference counting** è quella di *contare* il numero di *riferimenti* ad un dato oggetto allo scopo di determinare se ve n'è almeno uno ancora valido.
Se il conteggio arriva a zero, chiaramente l'oggetto *non è più raggiungibile dal root set* e può essere dis-allocato.
In Python viene adottato questo sistema, difatti ad ogni oggetto viene associata una variabile *contatore di riferimenti (RC)*.
Nel graph model dello heap, questa variabile conta il numero di *archi entranti* nel nodo/oggetto, questa proprietà è la *condizione invariante* che l'algoritmo deve soddisfare.

#### Inizializzazione del RC
L'inizializzazione del RC è effettuata dal *mutator* nel momento in cui l'oggetto viene creato.
Il codice Python riportato di seguito utilizza la primitiva di sistema `sys.getrefcount`.
Si deve tenere contro che la stessa chiamata di `sys.getrefcount` provoca l'aumento di una unità del valore del RC dell'oggetto passato come parametro.
```jupyter
import sys
A = [1,2]
sys.getrefcount(A)
```

#### Operazioni che modificano il RC
Il RC di un oggetto può essere cambiato:
- mediante *assegnamento*, cioè se un riferimento all'oggetto appare come parte destra di un assegnamento;
- se viene passato come *parametro* ad una funzione, perché l'oggetto viene *legato al parametro formale*;
- se viene inserito in un *oggetto contenitore*, ad esempio una lista.

#### Vantaggi e svantaggi
Il principale vantaggio dell'approccio basato su RC è che dis-allocare la memoria degli oggetti non più raggiungibili *non bisogna attendere* l'esecuzione periodica di un algoritmo.
La memoria può essere liberata *non appena il valore di RC arriva a zero*.
Un problema molto serio è invece la necessità di *proteggere gli accessi* ai contatori RC degli oggetti.
Se differenti thread potessero accedere simultaneamente ad un stesso RC (*race condition*) si potrebbero verificare situazioni di errore (*memory leak* o *dandling reference*).
Un secondo problema è la possibilità che l'esistenza di *riferimenti circolari* impedisca la corretta de-allocazione di oggetti.