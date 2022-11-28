Un **generatore** implementa lo stesso _protocollo_ di un [[iteratore]], ma è definibile in modo più semplice a partire dalla più comune nozione di [[funzione]].
In un generatore sono presenti due concetti:  una _generator function_ e il _generatore vero e proprio_.
Non c'è nessuna restituzione esplicita del generatore da parte della generator function.
Un generatore viene poi invocato usandolo come parametro della funzione built-in [[next]], ovvero inserendolo in un opportuno ciclo [[for]].

## Generator function
La **generator function** è una funzione a tutti gli effetti, che accetta parametri in ingresso e restituisce un _generator object_, o semplicemente generatore.
Il modo per riconoscere una **generator function** è l'uso della funzione [[yield]] al posto della [[return]].

## Esempio
```jupyter
def fibonacci(n):
	a = 0
	b = 1
	yield a
	for _ in range(n-2):
		yield b
		a,b = b,a+b
	yield b

fibo = fibonacci(6)

print(next)
```