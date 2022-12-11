Nel [[Protocollo TCP|TCP]] il mittente ed il destinatario, prima di iniziare il trasferimento dei segmenti contenenti i dati, instaurano una connessione.
Vengono per prima cosa *inizializzate delle variabili del TCP*:
- *Numeri di sequenza dei segmenti*.
- *Informazioni necessarie per la gestione del buffer di trasmissione e ricezione*.

Quando un client richiede una connessione invia un segmento speciale chiamato *`SYN` segment* al server.
Il client deve conoscere a chi spedire la richiesta, per cui nell'header del segmento deve specificare la *porta del server*.
Per accettare la connessione, il *server* deve essere già in attesa di ricevere connessioni.
