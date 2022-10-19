La __tupla__ è un tipo di dato _immutable_, è una sequenza lineare di oggetti, _di qualsiasi tipo_.
L'accesso ai singoli elementi di una tupla si realizza mediante un _indice numerico_ incluso fra parentesi quadre, oppure si può accedere a sequenze contigue tramite la notazione `[inizio:fine]`.
La _rappresentazione esterna_ prevede di separare da virgole gli elementi della struttura, racchiudendoli fra parentesi tonde.
Il numero di elementi che compongono la struttura ne costituisce la _lunghezza_.
```jupyter
T1 = (1,2,3)
print(T1[0])
print(T1[1:])
print(len(T1))
```
Essendo di tipo immutable la tupla `()` non è di alcuna utilità e anche la tupla di lunghezza uno è ambigua e quindi si mette sempre la virgola finale `(1,)`.