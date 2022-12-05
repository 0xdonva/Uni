L'idea alla base del **reference counting** è quella di *contare* il numero di *riferimenti* ad un dato oggetto allo scopo di determinare se ve n'è almeno uno ancora valido.
Se il conteggio arriva a zero, chiaramente l'oggetto *non è più raggiungibile dal root set* e può essere dis-allocato.
In Python viene adottato questo sistema, difatti ad ogni oggetto viene associata una variabile *contatore di riferimenti (RC)*.
Nel graph model dello heap, questa variabile conta il numero di *archi entranti* nel nodo/oggetto, questa proprietà è la *condizione invariante* che l'algoritmo deve soddisfare.

#### Inizializzazione del RC
