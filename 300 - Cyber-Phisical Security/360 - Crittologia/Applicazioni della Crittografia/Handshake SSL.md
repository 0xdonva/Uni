Il [[protocollo SSL]] utilizza una *combinazione di chiavi pubbliche e private*.
Usa sessione SSL inizia sempre con uno scambio di messaggi di handshake.
L'obbiettivo è quello di consentire al server di autenticarsi al client usando una tecnica a chiave pubblica e permette, sia al client sia al server, di cooperare per la creazione delle chiavi simmetriche usate per cifrare velocemente.
Eventualmente l'handshake permette anche al client di autenticarsi al server, ma questo è realizzabile in pochi casi: solo quando anche il client è dotato di certificato.

### Autenticazione del server SSL
Un browser dotato di SSL mantiene un elenco di Certification Authority affidabile e le relative chiavi pubbliche.
Quando il browser interagisce con un server Web *SSL-enhanced* ottiene da questi un certificato che contiene la chiave pubblica del server.
Il certificato è rilasciato dal server, poi firmato digitalmente da una CA presente dell'elenco delle CA affidabili del client.
Questa caratteristica consente al browser di *autenticare* il server prima che l'utente gli trasmetta informazioni riservate.

### Autenticazione del client
Garantisce il server sull'identità del client e fa uso di certificati rilasciati dalla CA del client.
Questa autenticazione è importante nel caso in cui il server sia un ente che vuole controllare l'identità del client.
L'autenticazione del client, sebbene supportata da SSL, è opzionale.

### Handshake versione TLS 1.3
![[Pasted image 20221214122655.png]]
