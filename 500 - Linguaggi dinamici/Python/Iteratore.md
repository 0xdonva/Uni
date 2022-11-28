In Python un **iteratore** è un oggetto su cui è possibile iterare, cioè *restituisce un elemento per volta* e implementa lo *iterator protocol* che consiste in due metodi:
- [[__iter__]](): restituisce l'oggetto iteratore.
- [[__next__]](): restituisce il prossimo valore dell'iteratore, se non ce ne sono più solleva una eccezione _StopIteration_.