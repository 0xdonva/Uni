Un garbage collector di tipo **tracing** procede all'individuazione degli oggetti ancora referenziabili attraverso una catena di riferimenti che parte dai cosiddetti *oggetti radice* (*variabili globali* e sullo stack, *variabili locali*, inclusi naturalmente i *parametri formali*).
L'insieme degli oggetti radice è detto *insieme radice* (*root set*).
Gli oggetti ancora referenziabili sono detti anche *raggiungibili*.
La definizione di oggetto raggiungibile è ricorsiva:
- Un *oggetto radice* è raggiungibile.
- Un oggetto *referenziato da un oggetto raggiungibile* è a sua volta raggiungibile.
Dopo aver individuato tutti gli oggetti raggiungibili si procede al *rilascio* degli oggetti *non più raggiungibili*.
I due principali algoritmi che si basano su questo principio sono:
- [[Mark and sweep]].
- [[Tri-color marking]].