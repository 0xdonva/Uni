## Idea di base
Associare ad un file di $NB$ blocchi una funzione che trasformi un valore di chiave $k_i$ in un numero di blocco $b_i$ tra $1$ ed $NB$:
- Una tupla viene memorizzata nel blocco $b_i$.
- Ad ogni blocco è associato un indirizzo nel disco.
- Un blocco può contenere 1 o più tuple.

Nel caso di organizzazione hash, il blocco prende il nome di bucket

La regola con cui ad una chiave $k$ viene associato un numero di blocco $b$ si chiama *funzione hash* o *algoritmo di hashing*.
Il file è ben utilizzato se:
- Ci sono pochi spazi vuoti, cioè se il fattore di "packing" (caricamento) è elevato: $Fp=m/M<1$, dove $M$ è il numero massimo di record per blocco e $m$ è il numero medio di record per blocco
- L'occupazione effettiva dei blocchi è vicina alla media.
$Fp$ basso sta a significare che il file è vuoto, $Fp$ vicino ad 1 sta a significare che molti blocchi sono pieni. Con i blocchi pieni si creano problemi di *overflow*.
Quando un blocco (es. $b_j$) è pieno ed una nuova tupla deve essere inserita poiché $FH$ (f. hash) gli ha assegnato quel blocco ($b_j$) allora si deve creare una *lista (catena) di overflow*.

L'**overflow** avviene per due motivi:
1. Ci sono più tuple con lo stesso valore chiave per cui $FH$ le manda nello stesso blocco.
2. $FH$ non è perfetta ed assegna due o più valori di chiave diversi lo stesso blocco del file (collisione).
Con lunghe liste di overflow si degrada l'efficienza $FH$ deve distribuire le tuple il più uniformemente possibile nei blocchi.
Osserviamo che:
- Più piccolo è il blocco rispetto alle tuple più è alto $Fp$ ma più probabile è l'overflow.
- Più grande è il blocco rispetto alle tuple più è basso $Fp$ ma è meno probabile l'overflow.

## Metodi per la funzione hash
### Mid-square
La chiave (convertita in numero se alfanumerica) è moltiplicata per se stessa ed i numeri centrali del quadrato vengono presi e normalizzati per rientrare nel "range" $NB$ del numero di blocchi del file.

### Divisione
La chiave $K$ viene divisa per il numero primo più vicino ad $NB$ ed il resto viene preso come numero del blocco.
Questo metodo non è un "randomizzatore", ma assegna valori successivi di $K$ a blocchi successivi.

### Shifting
Le cifre della chiave $K$ vengono divise in due (o più) gruppi, vengono spostate in modo da sovrapporsi per un numero di cifre pari al numero di cifre che rappresentano $NB$ blocchi, i frammenti di $K$ vengono sommati ed il risultato viene normalizzato.

### Folding
I frammenti vengono "ripiegati" (fold) su se stessi e poi sommati, le cifre in eccesso vengono eliminate.