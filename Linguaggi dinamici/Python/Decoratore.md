Una [[funzione]] __decoratore__ è una funzione "decora" con _codice aggiuntivo_ un'altra funzione.
In Python per la stessa costruzione esiste una _sintassi specifica_, molto efficace dal punto di vista comunicativo oltre che molto elegante.
Si tratta di uno dei numerosi casi di _zucchero sintattico_, in quanto le due scritture seguenti si equivalgono:
```python
@F
def G(...):
	...


G = F(G)
```

## Casi d'uso
I tipi casi d'uso dei decoratori sono:
- Trattamento dei _casi particolari_ di input che renderebbero meno chiaro il programma.
- Calcolo di _statistiche_ relative all'usa della funzione.
- Controllo delle _credenziali_.
- Attesa di eventi _asincroni_.