In Python il passaggio di valori avviene _per riferimento_, ciò accade esattamente è che l'identificatore locale viene _legato_ al valore dell'argomento nella chiamata.
```python
def f(x):
	# Qui esiste il legame x-->3
	...

z = 3 #Qui esiste il legame z-->3
f(z)
```
Se l'oggetto è [[Dato#Immutable|immutable]], il passaggio è assimilabile a quello che, in altri linguaggi, viene chiamato passaggio _per valore_, si può cambiare il legame locale ma non l'oggetto.
```python
def f(x):
	# Qui esiste il legame x-->3
	x = 1
	# Qui esiste il legame x-->1

z = 3 #Qui esiste il legame z-->3
f(z) 
# Qui esiste il legame z-->3
```
Se l'oggetto è [[Dato#Mutable|mutable]], la situazione iniziale è la stessa, cioè abbiamo binding che differiscono nel nome ma non nell'oggetto, tuttavia usare il binding locale può modificare l'oggetto.
```python
def f(L):
	# Qui esiste il legame L-->[1,2,3]
	L.append(4)
	# Qui esiste il legame L-->[1,2,3,4]

M = [1,2,3] #Qui esiste il legame M-->[1,2,3]
f(z) 
# Qui esiste il legame M-->[1,2,3,4]
```
Però anche nel caso di oggetto [[Dato#Mutable|mutable]], tuttavia, un _assegnamento locale a L_ modifica il binding locale ma non quello globale.
```python
def f(L):
	# Qui esiste il legame L-->[1,2,3]
	L = [1,2,3,4]
	# Qui esiste il legame L-->[1,2,3,4]

M = [1,2,3] #Qui esiste il legame M-->[1,2,3]
f(z) 
# Qui esiste il legame M-->[1,2,3]
```

## Tipi di parametri
### Posizionali
I parametri vengono definiti __posizionali__ perché, se il nome non viene specificato, il sistema procede sempre con l'ordine dettato dalla posizione.

### Keyword
I parametri formali di una [[Funzione]] possono prevedere un _valore di default_.
```python
def f(...,<nome>=<oggetto>,...)
```
Questo perché in fase di chiamata se il corrispondente argomento non viene indicato, nella [[Funzione]] il binding iniziale del parametro sarà con l'_oggetto presente nella definizione_.
Il binding dei parametri con valore di default (chiamati anche parametri __keyword__) può essere fatto secondo la posizione oppure specificando il nome.
I parametri keyword devono sempre _seguire quelli posizionali_ nella definizione.

## Numero indeterminato di parametri
Nella definizione di una [[Funzione]] si può specificare che il _numero di parametri è variabile_.
La variabilità può riguardare sia i parametri _posizionali_ che i parametri _keyword_, un nome preceduto da _un asterisco_ indica la presenza di 0 o più parametri posizionali mentre un nome preceduto da _due asterischi_ indica la presenza di 0 o più parametri keyword.
```python
def f(x, *y, a=5, **z):
    print(x)
    print(y)
    print(a)
    print(z)
```
