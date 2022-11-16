### Eliminazione delle gerarchie
Il modello relazionale non rappresenta le gerarchie, le gerarchie sono sostituite da entità e associazioni, e le tre possibili soluzioni sono:
1. Mantenimento delle entità con associazioni.
2. Collasso verso l'alto.
3. Collasso verso il basso.

#### mantenimento delle entita'
- Tutte le entità vengono mantenute.
- Le entità figlie sono in associazione con l'entità padre.
- Le entità figlie sono identificate esternamente tramite l'associazione.

#### collasso verso l'alto
Il collasso verso l'alto riunisce tutte le entità figlie nell'entità padre:
- Favorisce operazioni che consultano insieme gli attributi dell'entità padre e quelli dell'entità figlia: in questo caso si accede a una sola entità, anziché a due attraverso una associazione.
- Gli attributi obbligatori per le entità figlie diventano opzionali nel padre.

#### Collasso verso il basso
Nel collasso verso il basso si elimina l'entità padre trasferendone gli attributi su tutte le entità figlie:
- Una associazione del padre è replicata, tante volte quante sono le entità figlie.
- La soluzione è interessante in presenza di molti attributi di specializzazione.
- Favorisce le operazioni in cui si accede separatamente alle entità figlie.