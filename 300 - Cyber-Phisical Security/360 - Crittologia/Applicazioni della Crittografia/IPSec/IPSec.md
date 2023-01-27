## Obbiettivi
Poiché il livello network di Internet è tradizionalmente *connectionless*, lo si trasforma in un livello con connessioni logiche.
*Security Association* (*SA*) crea un canale logico a livello network.
La sorgente non è autenticata e il messaggio non ha garanzie di integrità per questo l'*Authentication Header* (*AH*) fornisce autenticazione della sorgente e l'integrità dei dati.
E infine per garantire la riservatezza l'*Encapsulation Security Payload* (*ESP*) aggiunge alle proprietà AH anche la crittografia del messaggio.

## Caratteristiche
**IPSec** non è solo un'estensione del protocollo IP è una vera e propria **architettura di sicurezza completa** per il traffico a livello di IP.
Inizialmente progettato per IPv6 e portato poi su IPv4.

## Componenti chiave
- **Security Associations** (**SA**): creazione e gestione di [[Security Association|SA]].
- **Security Protocols**: per l'integrità e autenticazione *[[Protocollo AH|AH]]* mentre per la riservatezza *[[Protocollo ESP|ESP]]*.
- **Internet Key Exchange** (**[[Protocollo IKE|IKE]]**): gestione delle chiavi simmetriche.

## Vantaggi e svantaggi
### Vantaggi
- Non richiede modifiche hardware e del software dei dispositivi di rete.
- Rendendo sicure tutte le comunicazioni a livello network, di conseguenza tutti i protocolli e le applicazioni che utilizzano IP beneficiano di un alto livello di sicurezza.

### Svantaggi
- Necessità di modifiche allo stack TCP/IP standard.
- È abbastanza complesso da gestire.
- È un protocollo di sicurezza punto-punto, non funziona per reti broadcast.