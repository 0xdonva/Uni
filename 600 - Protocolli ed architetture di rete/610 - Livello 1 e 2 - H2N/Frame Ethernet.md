I pacchetti scambiati a livello h2n vengono detti frame.
Indipendentemente dalla tipologia tutte le tecnologie [[Ethernet]] fanno uso dello stesso formato per il frame che trasmettono.

## Campi del frame
| Preambolo | Indirizzo destinazione | Indirizzo sorgente | Tipo | Dati    | CRC |
| --------- | ---------------------- | ------------------ | ---- | ------- | --- |
| 8 bytes   | 6                      | 6                  | 2    | 46-1500 | 4    |

### Preambolo
I primi sette byte hanno valore `10101010` e servono ad attivare gli adattatori dei riceventi e sincronizzare i loro orologi con quello del mittente.
L'ultimo byte ha valore `10101011`, la coppia `11` avvisano l'adattatore del ricevente che la fase di sincronizzazione è terminata e sta arrivando il contenuto vero e proprio.

### Indirizzo destinazione e sorgente
Contengono l'[[indirizzo MAC]] di sorgente e destinazione, quando un [[NIC]] riceve un frame [[Ethernet]] controlla se il campo destinazione coincide con il suo MAC

### Tipo
Permette a [[Ethernet]] di _multiplexare_ i protocolli del livello di rete, gli host potrebbero supportare protocolli dello strato di rete diversi da IP.
Gli host supportano i protocolli ARP e RARP, il campo tipo serve all'adattatore per sapere a quale dei protocolli dello strato di rete debba essere passato il campo dati di ciascun frame.

### Dati
Contiene i dati reali, l'unità massima trasferibile è 1500 byte, se i dati la superano va frammentato, mentre la dimensione minima è 46 byte.

### CRC
CRC è l'acronimo di _Controllo a Rindondanza Ciclica_ il cui scopo è di permettere all'adattatore che riceve i dati di rilevare la presenza di un errore nei bit del frame ricevuto.
Questo campo viene calcolato dal host quando trasmette il frame, lo ottiene dalla correlazione degli altri bit del frame escluso il preambolo.
Quando un host riceve ricalcola il CRC per vedere se tutto corrisponde.