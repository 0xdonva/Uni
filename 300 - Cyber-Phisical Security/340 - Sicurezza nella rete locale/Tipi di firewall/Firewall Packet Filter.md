Il __Firewall Packet Filter__ agisce a livello 3 e a livello 4 dello stack TCP/IP.
Bloccano o lasciano passare il traffico che attraversa il firewall definendo i protocolli, gli indirizzi IP e le porte che si possono o non possono utilizzare.
Spesso viene completato da funzionalità di routing per permettere l'instradamento dei pacchetti accettati all'interno della rete.
Quando un pacchetto arriva al packet filter, il firewall estrae alcune informazioni sull'header e, in base alle regole definite, o lo inoltra o lo scarta.

## Tecniche di filtraggio
### Static packet filtering
Prima tecnica ad essere implementata, considera i singoli pacchetti come entità individuali, non correlati tra loro.
##### Vantaggi
Tutti i pacchetti vengono analizzati come unità di informazione non correlata tra loro:
- basso costo computazionale ed economico.
- Non richiede il mantenimento di informazioni di stato.
- Semplice da implementare e gestire.
- Ottima scalabilità.
##### Svantaggi
Tutti i pacchetti vengono analizzati come unità di informazione non correlata tra loro...