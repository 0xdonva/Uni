**SSL** (**Secure Socket Layer**) è un protocollo *aperto e non proprietario* sviluppato da Netscape per avere la possibilità di creare "siti Web sicuri".
La versione attualmente utilizzata è la numero *3.1* che è diventata standard de facto da 1998.
Questo protocollo può essere utilizzato da tutti i protocolli applicativi non solo per la sicurezza del Web, è un protocollo indipendente dalla piattaforma e opera tra il livello 5 (applicativo) e il livello 4 (trasporto).

#### Proprietà garantite
- *Riservatezza della trasmissione*: c'è un handshake iniziale per definire una chiave simmetrica segreta, si crittografano i dati con la chiave segreta mediante algoritmo simmetrico.
- *Autenticazione*: è prevista la certificazione sia del client sia del server, l'identità degli interlocutori è definita mediante crittografia asimmetrica a chiave pubblica.
- *Integrità*: l'integrità del messaggio è garantita mediante un *Message Authentication Code* (*MAC*) che utilizza funzioni di hashing sicuro in grado di rilevare modifiche anche di un solo bit.

#### Organizzazione a due livelli
##### Primo livello: SSL Handshake
Il protocollo di handshake è usato per iniziare le sessioni con:
- Autenticazione tra client e server.
- Uso di cifratura a chiave asimmetrica e verifica mediante certificati.
- Negoziazione di un algoritmo di cifratura idoneo.
- Negoziazione delle chiavi relative all'algoritmo di cifratura.
- Scambio di chiave *master*.

Permette di controllare i parametri relativi al meccanismo di sicurezza.
Alert per il "peer messaging".
Metodi di compressione.

##### Secondo livello: SSL Record
Una volta ultimata la fase di handshake, il [[protocollo SSL Record]] provvede a trasferire i dati cifrati mediante la *chiave simmetrica di sessione* condivisa nella fase precedente.
Fornisce i servizi di sicurezza di base: responsabile di trasformare i dati delle applicazioni secondo le modalità concordate nella fase precedente.

## Sessione SSL
#### Riservatezza
Tutte le informazioni scambiate fra i due host sono cifrate dal software dell'host mittente e decifrate dal software dell'host destinatario con la stessa chiave simmetrica.
SSL fornisce anche un meccanismo per rilevare eventuali contraffazioni delle informazioni da parte di un intruso.

#### Integrità
Per garantire l'integrità del messaggio, SSL sfrutta una funzione hash sicura per creare il MAC
All'arrivo del *messaggio + MAC* cifrato, il destinatario:
- Decifra il MAC e il messaggio con la chiave simmetrica.
- Eventualmente decomprime e riassembla il messaggio.
- Calcola il digest e lo confronta con il digest del messaggio ricevuto.
- Se sono uguali, il messaggio può ritenersi integro e vien consegnato al processo applicativo superiore.