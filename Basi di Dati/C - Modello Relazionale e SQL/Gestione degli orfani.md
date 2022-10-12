## Orfani
Tuple che restano prive di padre a causa di cancellazioni e modifiche della tabella padre.

## Gestione degli orfani
#### Cascade
- Aggiornamenti su colonne riferite aggiornano tutte le colonne delle tuple con foreign key che si riferiscono ad esse.
- Cancellazioni di tuple riferite cancellano tutte le tuple contenenti riferimenti ad esse.

#### set null
- Aggiornamenti e cancellazione su colonne riferite causano la modifica delle colonne di foreign key a NULL.

#### Set default
- Aggiornamenti e cancellazioni di colonne riferite causano la modifica delle colonne di foreign key al valore di default.

#### no action
- Aggiornamenti e cancellazioni di colonne riferite sono proibiti se riferiti da almeno una tupla con foreign key.

