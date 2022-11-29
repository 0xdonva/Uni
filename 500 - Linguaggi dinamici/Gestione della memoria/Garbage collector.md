Il **garbage collector** (GC) opera nel modo seguente:
1. *Individua* oggetti che non potranno mai più essere referenziati dall'applicazione.
2. *Rilascia* la memoria relativa a tali oggetti.

Il GC deve soddisfare alcune proprietà importanti:
- *Correttezza*: il GC non deve mai disallocare oggetti ancora raggiungibili.
- *Efficienza*: sia in termini di tempo che di spazio.

Il GC *utilizza* una certa quantità di spazio per tenere traccia dell'accessibilità e per il *recupero* degli oggetti (overhead), il consumo però deve essere comunque *limitato*.
L'overhead in termini di tempo viene tipicamente valutato in termini di due quantità:
- *Latenza*: il tempo durante il quale il GC deve "fermare" l'esecuzione dell'applicazione.
- *Throughput*: la quantità di oggetti rilasciati ad ogni ciclo di garbage collection.

Esiste ovviamente un *trade-off* fra la latenza e il throughput.
I tre approcci principali alla realizzazione di un GC sono:
1. [[Tracing garbage collection]]
2. [[Reference counting garbage collection]]
3. [[Generational garbage collection]]