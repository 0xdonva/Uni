La **cifratura di Rivest, Shamir, Adleman** (**RSA**) è una cifratura creata al MIT negli anni '70.
Rivest, Shamir e Adleman sono riusciti ad individuare quello che serviva: non una funzione unidirezionale, ma **una funzione unidirezionale speciale** con possibilità di essere invertita assumendo di avere qualche dato.
Questa funzione:
- Permette a chiunque di cifrare un messaggio.
- È unidirezionale per tutti.
- 

##### Prima robustezza: Fattorizzazione
È basato sulla difficoltà di scomporre un numero nei suoi fattori primi.
La scomposizione è inevitabilmente un metodo "a forza bruta" in quanto bisogna provare tutti i numeri primi inferiori alla radice del numero per trovarli.
I crittografi lo considerano la base più solida su cui fondare un sistema di crittografia che non possa essere violato con metodi di [[Cifrari per sostituzione#Crittoanalisi dell'alfabeto sostitutivo|crittoanalisi statistica]].

##### Seconda robustezza: Aritmetica modulare
Sfruttare funzioni unidirezionali semplici di cui l'aritmetica modulare è ricca.
I numeri che ci interessano sono i numeri primi $p$ per i quali le potenze del $2$ garantiscono permutazione di tutti i numeri $\{1,2,...,p-1\}$