
Una [[Funzione]] in Python restituisce _sempre_ un oggetto, infatti l'esecuzione termina non appena viene eseguita un'istruzione __return__.
Subito dopo l'istruzione `return` può essere specificata un'espressione ed è precisamente il valore di questa che viene restituito al chiamante.
Se l'esecuzione termina senza che sia stata eseguita una _return_, la [[Funzione]] restituisce comunque l'oggetto _None_.
```jupyter
def sign(x):
	if x<0:
		return -1
	return 1
```
Una [[Funzione]] può anche restituire più di un valore, le quali vengono "impacchettate" in una [[Tupla]] che andrà successivamente "spacchettata".
