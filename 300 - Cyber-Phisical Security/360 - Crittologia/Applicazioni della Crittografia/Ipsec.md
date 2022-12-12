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
- **Security Protocols**: per l'integrità e autenticazione *AH* mentre per la riservatezza *ESP*.
- **Internet Key Exchange** (**IKE**): gestione delle chiavi simmetriche.

## Security Associations
*Accordo tra due entità per stabilire come trasmettere informazioni in modo sicuro*.
IPSec ha l'obbiettivo di supportare vari standard.
Questo porta ad avere una serie di parametri di sessione