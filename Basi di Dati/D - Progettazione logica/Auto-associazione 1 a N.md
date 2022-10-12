È traducibile con una sola relazione che contiene due volte l'attributo chiave: una volta come chiave ed una come riferimento all'istanza connessa, con un nome diverso per specificare il ruolo.
![[Pasted image 20220412152931.png]]
```
DIPENDENTE(_MATR_,NOME,CAPO)
	FK: CAPO REFERENCES DIPENDENTE
```
