Una __funzione__ è un blocco di codice che viene eseguito _su chiamata_, al quale si possono passare dati (detti [[Parametro|parametri]]) e che restituisce altri dati (i _risultati_).
La signature di una funzione è questa:
```python
def <nome> ({<lista parametri posizionali>}{,<lista parametri keyword>}):
	<blocco>
```

## Manipolazione di funzioni
In Python essendo le funzioni _first class object_, possono essere assegnate ad una _[[variabile]]_ o possono essere passate come _[[parametro]]_ ad una _funzione_.
```jupyter
def square(x):
    return x*x

def f(g,x):
	return g(g(3))
s = square
s(3)
f(s,3)
```

## Funzioni anonime
In Python possono essere definite __funzioni anonime__ usando la così detta _lambda notation_.
Il caso d'uso tipico è quando essa deve essere usata come _[[parametro]] di un'altra funzione_.
```jupyter
square = lambda x: x**2   # Funzione anonima, assegnata "dopo" ad un identificatore
y = square(5)
print(y)
```
