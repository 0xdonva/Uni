__`__getattribute__`__ è un [[metodo magico]] che viene invocato per gli _accessi in lettura_ di una [[classe]].
`__getattribute__`, [[__getattr__]] e [[__setattr__]] sono metodi che sono definiti nella classe `object` ed ereditati, a _meno di overriding_, da tutte le classi.
Ridefinendo questo metodo il programmatore ha la possibilità di controllare il processo di _ricerca_ e _accesso agli attributi_.
