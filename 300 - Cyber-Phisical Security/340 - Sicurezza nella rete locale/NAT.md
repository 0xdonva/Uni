Il __NAT router__ si interpone tra la rete locale di una organizzazione e Internet con i seguenti compiti:
- Mappa gli indirizzi IP tra due domini.
- Garantisce la trasparenza del routing tra gli _end system_.
- "Moltiplica" la possibilità di interconnessioni di host di una organizzazione.
- Aumenta la sicurezza evitando di rendere visibili all'esterno alcuni computer di una organizzazione

### Vantaggi
- Distrugge la semantica della comunicazione Internet _stateless_ e _end-to-end_, che era uno dei fondamenti su cui è stata progettata la rete Internet in quanto gli host interni non possono essere raggiunti direttamente dall'esterno ma solo tramite controllo centralizzato.
- Soluzione economica, relativamente facile, veloce.
- Consente la massima flessibilità nella gestione interna degli indirizzi senza necessità di richiedere alcun permesso al proprio ISP né di comunicare ad altri eventuali modifiche.

### Svantaggi
- Distrugge la semantica della comunicazione Internet _stateless_ e _end-to-end_.
- La così detta _NAT box_ modifica i pacchetti al volo: questo richiede modifiche a livello di informazioni _application_ e non solo l'header del datagramma IP, è necessario usare dei gateway NAT box a livello applicazione.