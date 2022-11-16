La dipendenza funzionale è un vincolo di integrità per il [[Modello Relazionale]].
La dipendenza funzionale si può definire formalmente:
```Definizione
Data una relazione R definita su uno schema S(X) e due sottoinsiemi di attributi Y e Z non vuoti di X, esiste una dipendenza funzionale Y->Z, se, per ogni coppia di tuple t1 e t2 aventi lo stesso valore di Y risulta che hanno lo stesso valore di Z.
```

#### Attenzione
Se prendiamo la chiave K della relazione R si verifica facilmente che esiste una dipendenza funzionale tra K ed ogni attributo dello schema.
Infatti per definizione di chiave esiste un solo valore di K in R e quindi la dipendenza di sui sopra è banalmente soddisfatta.

Le [[Ridondanze e anomalie]] sono causate da dipendenze X $\rightarrow$ Y tali che X non contiene la chiave di relazione.
Una relazione R è in forma normale (Boyce e Codd) se, *per ogni dipendenza X $\rightarrow$ Y in R, X contiene una chiave K di R (X è super-chiave)*.
Una relazione non in forma normale è possibile che venga scomposta in due o più relazioni in forma normale.
La scomposizione si può attuare effettuando proiezioni in modo tale da ottenere che ciascuna dipendenza funzionale corrisponda ad una relazione separata.

Quando la relazione originale è ricostruibile con il join la scomposizione è *corretta* e si dice essere *senza perdita*.

Scomposizioni errate possono generare relazioni che ricongiunte con il join, producono relazioni con dati incerti si ha quindi una perdita di informazioni.