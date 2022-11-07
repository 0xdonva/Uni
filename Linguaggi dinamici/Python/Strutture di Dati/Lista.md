La __lista__ è un tipo di [[dato]] _mutable_, è una sequenza lineare di oggetti, _di qualsiasi tipo_.
L'accesso ai singoli elementi di una [[tupla]] si realizza mediante un _indice numerico_ incluso fra parentesi quadre, oppure si può accedere a sequenze contigue tramite la notazione `[inizio:fine]`.
La _rappresentazione esterna_ prevede di separare da virgole gli elementi della struttura, racchiudendoli fra parentesi quadre.
Il numero di elementi che compongono la struttura ne costituisce la _lunghezza_.
```jupyter
L = [1,2,3]
print(L[0])
print(L[1:])
print(len(L))
```
Essendo _mutable_ è possibile modificare selettivamente, aggiungere o eliminare un elemento.

## Metodi delle liste
### Append
Permette di aggiungere un elemento in fondo alla lista:
```jupyter
list.append(L,4)
print(L)
```

### Extend
Permette di estendere la lista con un'altra lista:
```jupyter
list.extend(L,[5,6])
print(L)
```