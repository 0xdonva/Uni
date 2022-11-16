Da [[Python]] 2.2 __ogni dato è un oggetto__, proprio come inteso nella programmazione ad oggetti, cioè è _istanza_ di una qualche [[Classe]] (o tipo perché vengono usati come sinonimi).
In [[Python]] pure le funzioni o le stesse classi sono oggetti.

## Tipi da dato
I dati in Python possono essere semplici o strutture di dati:

### Semplici
I tipi semplici predefiniti in Python sono gli _[[Int e Float|interi]]_, i _[[Int e Float|float]]_, i _[[Bool|booleani]]_ e le _[[String|stringhe]]_.
Infatti non esiste il tipo di dato _carattere_ ma quest'ultimo è solo una stringa di lunghezza 1.

### Struttura
Uno dei tanti punti di forza di Python è la ricca dotazione di _dati strutturati_ predefiniti: _[[Tupla|tuple]]_, _[[Lista|liste]]_, _[[Insieme|insiemi]]_ e _[[Dizionario|dizionari]]_.

### Immutable
Un tipo di dato __immutable__ è un tipo di dato che se viene modificato modificato, viene modificata anche la sua identità.
Perché il contenuto in se per se viene cambiato e quindi anche il punto di accesso in memoria, ovvero la sua identità, cambia.
Questo si verifica per i quattro tipi semplici di Python.
Permette di evitare _side-effect_ potenzialmente pericolosi, per via della notevole pulizia concettuale, però aumenta l'_overhead_ complessivo del programma e quindi l'uso della _memoria_.

### Mutable
Un tipo di dato __mutable__ è un tipo di dato che se cambia il suo contenuto la sua identità non cambia, quindi il punto di accesso rimane il precedente.
Questo viene utilizzato nei linguaggi imperativi il che li rende meno puliti ma più efficienti.