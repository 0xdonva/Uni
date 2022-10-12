Viene tradotta con: una relazione per l'entità e una per l'associazione, quest'ultima contiene due volte la chiave dell'entità, è necessario, però modificare i nomi degli attributi, per non avere omonimia.
![[Pasted image 20220412152549.png]]
```
STATO(_NOME_, AREA)
CONFINA(_STATO-A_,_STATO-B_)
	FK: STATO-A REFERENCES STATO
	FK: STATO-B REFERENCES STATO
```
