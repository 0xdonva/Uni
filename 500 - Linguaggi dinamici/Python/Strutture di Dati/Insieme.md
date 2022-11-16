Un __insieme__ è un tipo di [[Dato]] _immutable_, è caratterizzato dagli elementi che contiene e non ci possono essere due elementi _uguali_.
Questi insiemi modellano in modo alquanto fedele gli insiemi definiti nella Matematica.
La _rappresentazione esterna_ usa le parentesi graffe ma l'insieme vuoto non è `{}`, ma `set()`, perché questa scrittura è riservata ai [[Dizionario|dizionari]].
Gli insiemi non sono sequenze, _non ha importanza l'ordine_ con cui gli elementi sono scritti e quindi non esiste un accesso per posizione.
La _manipolazione_ avviene attraverso metodi che implementano le operazioni insiemistiche.
```jupyter
S = {1,2,3,3}
T = {3,4,5}
E = set()
print(S)
set.intersection(S,T)
set.union(S,T)
set.difference(S,T)
```
