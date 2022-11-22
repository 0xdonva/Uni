In Python la definizione di una [[classe]] può menzionare più _superclassi_, Python cioè supporta l'__ereditarietà__ _multipla_.

## Definizione
Una classe `A` è una _superclasse_ di `B` se `A` è una classe base di `B` oppure se è una _superclasse di una classe base di `B`_.
La classe `object` è antenata di qualsiasi classe.
```jupyter
class A:
	pass

class B(A):
	pass
```

## MRO
%%PYTHON3.IPYNB%%

### Overriding degli attributi
Se più _superclassi_ di una data classe `C` definiscono lo stesso attributo (cioè usano lo stesso nome), da `C` e dagli oggetti di `C` ciò che è visibile è solo il nome definito dalla _classe che prima si incontra nell'MRO_.
Python non supporta l'_overloading_ dei metodi, questo perché l'interprete non considera la differente _signature_ dei due metodi, ma solo il nome

### Intervenire sul protocollo
Il comportamento di Python relativo alla ricerca di un attributo non è rigidamente _cablato nell'interprete_.
L'interprete si avvale invece di alcuni metodi che forniscono il comportamento default osservato ma che sono _accessibili al programmatore_.
I metodi in questione, che sono dei [[Metodo magico|metodi magici]], sono tre e precisamente:
- [[__getattribute__]]
- [[__getattr__]]
- [[__setattr__]]