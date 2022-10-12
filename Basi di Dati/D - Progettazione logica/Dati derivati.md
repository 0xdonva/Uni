Un dato derivato è un dato che può essere ottenuto attraverso una serie di operazioni da altri dati:
- *Vantaggi*: a tempo di accesso non è richiesta alcuna operazione per ricavare il valore dell'attributo.
- *Svantaggi*: occorre eseguire operazioni di aggiornamento per mantenere la consistenza dei dati, si spreca memoria.
Possono derivare da tante situazioni:
- Attributi derivabili da altri attributi della stessa entità o associazione.
- Attributi derivabili da attributi di altre entità o associazioni.
- Attributi derivabili da operazioni di conteggio di istanze.
- Attributi derivabili dalla composizione di altre associazioni.

## Tipi di operazioni
### Lettura
In caso di visione di una istanza viene effettuata una operazione di lettura.

### Scrittura
In caso di inserimento di una nuova istanza o cancellazione di una istanza esistente è necessaria una scrittura.

### Lettura e scrittura
In caso di aggiornamento di una istanza esistente è necessaria prima una lettura e poi una scrittura.

## Calcolo della cardinalità
In generale, per spostarsi da un'entità A ad una B, è necessario calcolare la cardinalità di accessi all'associazione X.
![[Pasted image 20220507162140.png|500]]
Per farlo, dobbiamo prima di tutto guardare la cardinalità dell'associazione dal lato dell'entità A, se la cardinalità minima coincide con quella massima, questa coincide con la cardinalità di accessi a X e a B.

In tutti gli altri casi, lo schema E/R non ci aiuta a stimare la cardinalità e dovremo fare il calcolo sfruttando la tabella dei volumi:
![[Pasted image 20220507162659.png|500]]

A volte, la tabella dei volumi non contiene in esplicito le informazioni per tutte le entità e associazioni, perché queste possono essere desunte  dallo schema. Per poter effettuare il calcolo visto, è quindi utile prima di tutto completarla:
![[Pasted image 20220507162936.png|500]]