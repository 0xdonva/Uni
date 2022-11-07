Una __funzione__ è un blocco di codice che viene eseguito _su chiamata_, al quale si possono passare dati (detti [[Parametro|parametri]]) e che restituisce altri dati (i _risultati_).
La signature di una funzione è questa:
```python
def <nome> ({<lista parametri posizionali>}{,<lista parametri keyword>}):
	<blocco>
```

## Manipolazione di funzioni
In Python essendo le funzioni _first class object_, possono essere assegnate ad una _variabile_ o possono essere passate come _parametro_ ad una _funzione_.
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
In Python possono essere definite __funzioni anonime__ usando la cosidetta