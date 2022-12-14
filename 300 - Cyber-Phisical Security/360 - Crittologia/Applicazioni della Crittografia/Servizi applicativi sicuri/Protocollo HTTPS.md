Il **protocollo HTTPS** (**Hyper-Text Transfer Protocol over Secure Socket Layer**) è l'attuale standard per la connessione a siti Web.
È una versione moderna dell'HTTP infatti la `s` significa che il sito Web utilizza TLS per cifrare i dati nel momento in cui vengono trasmessi tra il client e il server.
Quindi tramite [[Protocollo SSL]] permette l'autenticazione del server e comunicazioni `client -> server` cifrate.
Il protocollo utilizza la porta `443`.
A differenza di HTTP, *HTTPS è un protocollo stateful*:
- Sia il client che il server devono tenere traccia delle chiavi private per garantire continuità nella comunicazione per *tutta la sessione*.
- A livello HTTP il concetto di sessione si emula con *cookie*.

Per quanto riguarda le prestazioni HTTPS è *molto più oneroso* perché SSL è molto più oneroso di TCP.
Mentre per l'autenticazione ogni browser contiene all'interno un certificato di default HTTPS.
Soprattutto una volta creata la connessione sicura, l'interazione è protetta da *IP spoofing* e *masquerading* perché le informazioni non sono leggibili senza le chiavi private.