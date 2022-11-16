In [[Python]] viene utilizzata la __tipizzazione dinamica__: il [[Dato#Tipi da dato|tipo]] non è fissato (con una dichiarazione) a tempo di compilazione ma può cambiare nel tempo di esecuzione.
Questo vuol dire che un oggetto può acquisire durante la sua creazione un tipo di oggetto, es. _int_, e poi durante la vita del programma vedersi assegnato un altro tipo di oggetto.
```jupyter
a = "Informatica"
print(type(a))
a = 1
print(type(a))
```
Python consente gli _assegnamenti multipli_ e _simultanei_, inoltre permette anche lo _scambio di valore_.
```jupyter
a = b = 1
c,d = 2,3
c,d = d,c
```
