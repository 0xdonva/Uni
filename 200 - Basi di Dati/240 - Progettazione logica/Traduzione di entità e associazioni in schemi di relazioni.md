## Traduzione standard
Ogni entità è tradotta con una relazione con gli stessi attributi.
Ogni associazione è tradotta con una relazione con gli stessi attributi, cui si aggiungono gli identificatori di tutte le entità che essa collega.

## Altre traduzioni
La traduzione standard è sempre possibile ed è l'unica possibilità per le associazioni $N$ a $M$.
Altre forme di traduzione delle associazioni sono possibili per altri casi di cardinalità (1 a 1, 1 a N).
Le altre forme di traduzione:
- Danno origine a un minor numero di relazioni e generano quindi uno schema più semplice.
- Richiedono un minor numero di join per la navigazione attraverso un'associazione, ovvero per accedere alle istanze di entità connesse tramite l'associazione.
- Penalizzano le operazioni che consultano soltanto gli attributi di una entità che è stata fusa.

#### [[Associazione binaria 1 a n]]
#### [[Associazione binaria 1 a 1]]
#### [[Auto-associazione N a M]]
#### [[Auto-associazione 1 a N]]
#### [[Auto-associazione 1 a 1]]
#### [[Associazione n-aria]]
