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

## Ereditarietà multipla
