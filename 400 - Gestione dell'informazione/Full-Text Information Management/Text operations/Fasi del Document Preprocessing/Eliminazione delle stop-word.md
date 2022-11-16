Il concetto che sta alla base dell'__eliminazione delle stop-word__ è quello di filtrare le parole con valori di discriminazione molto bassi.
Questo perché una parola molto frequente è inutile per lo scopo della ricerca quindi eliminando congiunzioni, articoli, pronomi, ecc., la dimensione della struttura indicizzata diminuisce di molto.

## Funzionamento
Il procedimento consiste nel ottenere l'output dell'[[Analisi lessicale del testo]] e da lì rimuovere ogni stop-word possibile, questo può essere fatto cercando la parola in una lista di stop-word già date.