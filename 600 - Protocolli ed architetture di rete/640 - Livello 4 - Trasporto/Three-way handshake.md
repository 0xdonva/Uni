Nel [[Protocollo TCP|TCP]] il mittente ed il destinatario, prima di iniziare il trasferimento dei segmenti contenenti i dati, instaurano una connessione.
Vengono per prima cosa *inizializzate delle variabili del TCP*:
- *Numeri di sequenza dei segmenti*.
- *Informazioni necessarie per la gestione del buffer di trasmissione e ricezione*.

## Instaurazione di una connessione
Quando un client richiede una connessione invia un segmento speciale chiamato *`SYN` segment* al server.
Il client deve conoscere a chi spedire la richiesta, per cui nell'header del segmento deve specificare la *porta del server*.
Per accettare la connessione, il *server* deve essere già in attesa di ricevere connessioni.
Il segmento `SYN` del client include:
- *Initial Sequence Number* (*ISN*) del client.
- *Maximum Receive Window* (*MRW*) del client.
- *Maximum Segment Size* (*MSS*).
- Non ha *payload*.

Il segmento `SYN` del serve include:
- *Initial Sequence Number* (*ISN*) del server.
- *`ACK`* del server: `client_ISN+1`.
- *Maximum Receive Window* (*MRW*) del server.
- *Maximum Segment Size* (*MSS*).
- Non ha *payload*.

![[Pasted image 20221211162545.png]]

## Chiusura "polite" della connessione
Essendo full- duplex, va chiusa da entrambe le parti:
- Il client invia un segmento controllo con bit `FIN`=1 al server.
- Il server riceve `FIN`, invia `ACK`.
- Il server chiude la connessione lato client-server ed invia `FIN`=1 al client.
- Il client riceve il segmento `FIN`=1 ed invia `ACK`.
- Il server riceve `ACK`.
- Il client attende il timeout dell'`ACK` inviato, allo scadere anche la connessione lato server-client viene chiusa.

Il client TCP attende per un tempo `TIME_WAIT` prima di chiudere definitivamente la connessione per poter gestire queste situazioni anomale.

## C