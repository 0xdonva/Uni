In Python 3 tutti i [[Dato#Tipi da dato|tipi]] sono __classi__.
Allo stesso modo, _ogni oggetto Python è istanza di una classe_.
In base a quest'ultima affermazione possiamo dire che esiste un punto di _singolarità_, ovvero una classe `T` è istanza di se stessa, se no sarebbe una sequenza infinita di istanze.
Questo punto di _singolarità_ è la classe `type`.
In Python è anche logico arrivare alla conseguenza che non ha senso parlare di attributi di classe e attributi di istanza, esistono gli _oggetti_ e i loro _attributi_.

## Creazione di classi e oggetti
La definizione di una classe Python richiede di specificare _quattro tipi di informazione_:
1. Il _nome_ della classe.
2. L'indicazione (opzionale) delle classi da cui essa eredita direttamente (cioè le sue _classi base_).
3. L'indicazione (opzionale) della classe di cui essa è istanza, ovvero il suo _tipo_.
4. Gli _attributi_ che fanno parte della classe
La seguente semplice definizione non è la più generale possibile ma è ampiamente sufficiente:
```python
class C{(B1,B2,...,BK)}:
	<elenco di attributi>
```
Python ammette [[ereditarietà]] multipla, è anche possibile non specificare _nessuna classe base_ nella definizione.
In tal caso, la classe eredità comunque da una classe di default, che è la _radice della catena ereditaria_.
Tale classe, che naturalmente include metodi che garantiscono le proprietà fondamentali delle classi, si chiama `object`.

## Istanziazione di una classe
In Python il processo di istanziazione di una classe può essere _minuziosamente controllato_, è però anche possibile specificare solo l'informazione minima necessaria, sfruttando il _comportamento di default dell'interprete_.
La creazione di un oggetto in Python procede in due fasi, separate e _accessibili al programmatore_: la creazione vera e propria dell'oggetto e la _creazione e inizializzazione degli attributi_.
Il metodo che crea e inizializza gli attributi si chiama `__init__` e, in quanto [[Metodo magico]], non necessita di essere chiamato esplicitamente.
```jupyter
class C:
	def __init__(self,x,y):
		self.x = x
		self.y = y
```
Il metodo `__init__` ha tre parametri, dei quali il primo è una convezione universale chiamarlo `self`, che viene legato nella chiamata all'oggetto appena creato, il resto sono parametri che servono al programmatore.

## Accesso agli attributi di una classe
In Python i metodi non sono così strettamente legati alle classi