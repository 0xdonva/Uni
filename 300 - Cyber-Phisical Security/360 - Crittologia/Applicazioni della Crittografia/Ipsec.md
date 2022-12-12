## Obbiettivi
Poiché il livello network di Internet è tradizionalmente *connectionless*, lo si trasforma in un livello con connessioni logiche.
*Security Association* (*SA*) crea un canale logico a livello network.
La sorgente non è autenticata e il messaggio non ha garanzie di integrità per questo l'*Authentication Header* (*AH*) fornisce autenticazione della sorgente e l'integrità dei dati.
E infine per garantire la riservatezza l'*Encapsulation Security Payload* (*ESP*) aggiunge alle proprietà AH anche la crittografia del messaggio.

## Caratteristiche
**IPSec** non è solo un'estensione del protocollo IP è una vera e propria **architettura di sicurezza completa** per il traffico a livello di IP.
Inizialmente progettato per IPv6 e portato poi su IPv4.

## Componenti chiave
- **Security Associations** (**SA**): creazione e gestione di SA.
- **Security Protocols**: per l'integrità e autenticazione *[[protocollo AH|AH]]* mentre per la riservatezza *[[Protocollo ESP|ESP]]*.
- **Internet Key Exchange** (**[[Protocollo IKE|IKE]]**): gestione delle chiavi simmetriche.

## Security Associations
*Accordo tra due entità per stabilire come trasmettere informazioni in modo sicuro*.
IPSec ha l'obbiettivo di supportare vari standard.
Questo porta ad avere una serie di parametri di sessione che devono essere negoziati prima di comunicare.
Un host può avere diverse connessioni attive in contemporanea, ognuna è determinata univocamente da un *SA identifier*.
Le *SA sono unidirezionali*.

### Componenti principali
#### Security Policy Database (SPD)
Ogni host che implementa IPSec è configurabile per utilizzare determinati algoritmi e protocolli.
SPD contiene le security policy da applicare ai diversi tipi di comunicazione, serve per associare ad ogni parametro da negoziare uno o più "valori" accettabili.
Può essere configurato manualmente o collegato ad un sistema automatico.

#### Security Association Database (SAD)
Elenco delle SA attive e delle relative caratteristiche.

### Modalità realizzative
#### Transport Mode
È una connessione host-to-host e viene usato dagli end-point e non dai gateway.
![[Pasted image 20221212123623.png]]
##### Vantaggi
L'unico modo possibile qualora sia necessario identificare e differenziare i nodi in base al loro indirizzo IP.

##### Svantaggi
Ogni host che vuole comunicare deve avere tutto il software necessario ad implementare IPSec.
La complessità di gestione cresce all'aumentare del numero di nodi comunicanti.

#### Tunnel Mode
Connessione gateway-to-gateway.
![[Pasted image 20221212123951.png]]
##### Vantaggi
- Nel percorso tra i gateway è impossibile risalire agli IP della sorgente e della destinazione reali.
- Solo i gateway devono avere il software IPSec.
- La complessità della gestione non aumenta all'aumentare del numero di host.

##### Svantaggi
- Impossibile differenziare i nodi in base all'IP.
- Computazionalmente oneroso: servono gateway potenti.