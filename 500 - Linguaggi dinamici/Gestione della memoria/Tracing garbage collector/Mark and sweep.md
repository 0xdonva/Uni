Si tratta di una dei *primi algoritmi* di [[tracing garbage collection]].
Ad ogni oggetto viene associato un *flag* che viene utilizzato dall'algoritmo di garbage collection.
Quando l'oggetto viene creato il bit è settato al valore $0$.
Nella fase di **Mark**, il bit negli oggetti del root set, e in quelli via via raggiungibili a partire dal root set, viene settato al valore $1$.
La fase di Mark equivale ad un *graph traversal*, come per esempio la *ricerca in profondità*.
Al termine della fase di Mark, gli oggetti non più raggiungibili sono caratterizzati dal valore $0$ del flag.
Nella fase di **Sweep** tali oggetti sono dunque dis-allocati mentre il flag degli oggetti raggiungibili viene riportato al valore $0$.
L'algoritmo viene ripetuto periodicamente.

#### Limiti dell'algoritmo
L'algoritmo è semplice ma *poco performante*.
L'esecuzione del programma deve essere *interrotta* durante l'intera esecuzione dell'algoritmo di garbage collection, il che comporta un'*alta latenza*.
L'elevata latenza deriva dal fatto che la memoria deve essere scansionata più volte: sia durante la fase di Mark solo i *living object* sia durante la fase di Sweep su tutto lo *heap*.
Naturalmente tutto ciò comporta problemi in sistemi che necessitano di basse latenze di risposta o comunque applicazioni con elevato *working set*.