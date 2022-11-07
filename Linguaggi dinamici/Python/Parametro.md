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
def f(x):
	# Qui esiste il legame x-->3
	x = 1
	# Qui esiste il legame x-->1

M = [1,2,3] #Qui esiste il legame M-->3
f(z) 
# Qui esiste il legame z-->3
```