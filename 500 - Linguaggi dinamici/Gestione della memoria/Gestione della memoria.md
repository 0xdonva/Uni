Quando si parla di gestione della memoria, si intende di regola la **gestione dello heap**.
Esistono fondamentalmente due approcci:
- [[Gestione manuale della memoria]]
- [[Gestione automatica della memoria]]

## Allocazione della memoria
Lo **heap** è quella porzione di memoria che può essere acceduta anche al di fuori del contesto di esecuzione in cui è stata allocata.
Un oggetto memorizzato nello heap può essere acceduto mediante *riferimento diretto* oppure tramite una struttura intermedia i cui elementi sono detti *handle*, che a sua volta referenzia l'oggetto.
Il riferimento tramite handle introduce un *extra-overhead* di memoria ma garantisce maggiore efficienza nella *rilocazione* degli oggetti.
Quando il programma effettua una richiesta di memoria il modulo di allocazione *individua* un'opportuna area libera nel *pool* e ne restituisce l'indirizzo, nel caso il pool sia esaurito interverrà il *sistema operativo*.