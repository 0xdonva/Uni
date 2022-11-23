Il __Firewall Packet Filter__ agisce a livello 3 e a livello 4 dello stack TCP/IP.
Bloccano o lasciano passare il traffico che attraversa il firewall definendo i protocolli, gli indirizzi IP e le porte che si possono o non possono utilizzare.
Spesso viene completato da funzionalità di routing per permettere l'instradamento dei pacchetti accettati all'interno della rete.
Quando un pacchetto arriva al packet filter, il firewall estrae alcune informazioni sull'header e, in base alle regole definite, o lo inoltra o lo scarta.

## Tecniche di filtraggio
### Static packet filtering
Prima tecnica ad essere implementata, considera i singoli pacchetti come entità individuali, non correlati tra loro.
##### Vantaggi
Tutti i pacchetti vengono analizzati come unità di informazione non correlata tra loro:
- _basso costo computazionale_ ed _economico_.
- _Non richiede_ il mantenimento di informazioni di stato.
- _Semplice_ da implementare e gestire.
- _Ottima scalabilità_.
##### Svantaggi
Tutti i pacchetti vengono analizzati come unità di informazione non correlata tra loro:
- Non è in grado di riconoscere pacchetti _appartenenti_ e _correlati_ ad una _connessione già aperta_.
- Occorre coprire numerosi buchi nel firewall per garantire una comunicazione bidirezionale valida per tutti i protocolli.
- Vulnerabile a tecniche elementari di _firewalking_.

### Stateful packet filtering
Analizza gli header di livello 3 e 4, non analizza header/payload a livello applicazione.
La dinamicità consiste nella capacità di:
- Distinguere le connessioni già aperte da quelle nuove.
- Mantenere tabelle di stato con le informazioni relative alle connessioni attive.
- Adattare dinamicamente le regole utilizzate per il filtraggio in base alle informazioni di stato.
##### Vantaggi
- Riconosce pacchetti appartenenti ad una connessione già aperta.
- Le risposte provenienti dall'esterno a connessioni legittime vengono autorizzate da regole temporanee, istanziate dinamicamente e automaticamente.
- Le regole temporanee sono attive solo per il tempo strettamente necessario.
- Non è necessario aprire buchi permanenti.
##### Svantaggi
- Non è in grado di riconoscere pacchetti correlati ad una connessione già aperta.
- Richiede maggiori quantità di memoria per mantenere informazioni relative alle connessioni.
- Richiede maggiore capacità computazionale.