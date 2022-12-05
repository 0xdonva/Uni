Si basa sull'algoritmo di Dijkstra, come nel [[Mark and sweep]] gli oggetti vengono rappresentati come un *grafo orientato*.
L'algoritmo partiziona l'insieme dei nodi in tre sottoinsiemi, identificati dai colori:
- *Bianco*: sono i nodi candidati alla rimozioni, cioè quei nodi che non sono (ancora) stati raggiunti dalla visita.
- *Grigio*: sono i nodi che sono stati raggiunti ma che *non sono finiti*, con finiti si intende che tutti i riferimenti esterni sono stati visitati.
- *Nero*: sono i nodi *finiti*.

Inizialmente tutti i nodi del root set sono grigi, tutti gli altri sono bianchi e il gruppo dei neri è *vuoto*.
Al termine di questo procedimento la memoria relativa ai nodi *bianchi* viene rilasciata.

#### Efficienza dell'algoritmo
Il **Tri-color marking** è *sensibilmente più efficiente* del [[Mark and sweep]].
L'algoritmo può infatti essere eseguito in maniera interlacciata con la computazione dell'interprete.
La colorazione iniziale avviene nel momento in cui l'oggetto viene creato.
Inoltre, l'interprete è libero di accedere qualsiasi parte del grafo, i *mutator* possono allocare nuovi nodi mentre il *garbage collector* determina quelli raggiungibili.
L'unico requisito per la correttezza è che venga mantenuta valida la *condizione invariante*.
L'esecuzione del programma deve essere interrotta solo durante lo svolgimento della *terza fase*, quella della de-allocazione della memoria.
