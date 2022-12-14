Un __router__ è un dispositivo il cui compito è quello di _instradare_ i pacchetti nella rete da qualsiasi altro host, sulla base dell'[[Indirizzo IP]] destinazione incluso nel pacchetto stesso.

## Inoltro pacchetti hp-by-hop
I router si passano i pacchetti hop-by-hop: nessuno decide il percorso complessivo, ma solo il router successivo.
Infatti un host che invia un pacchetto all'_esterno della propria rete locale_ deve decidere tramite router di inviarlo: quest'ultimo viene detto _source router_.
Ogni router deve decidere a sua volta il router (_next-hop router_) a cui inoltrare il pacchetto.
Infine il router di arrivo viene chiamato _destination router_.

## Funzionamento del router
Estrae l’[[Indirizzo IP]] del destinatario `D` dall’header del pacchetto e determina il suo `netid N`:
1. Se `N` corrisponde ad una rete connessa direttamente al router, consegna il pacchetto al destinatario `D` sulla rete (ciò comporta la risoluzione di `D` nel corrispondente indirizzo fisico e l’invio del frame via Ethernet) 
2. Se la tabella contiene un router per la rete `N`, invia il pacchetto al next-hop router specificato nella tabella. 
3. Se la tabella contiene un router di default, invia il pacchetto a quel router.
4. Altrimenti, si verifica un errore di routing.
Per effettuare tutte queste operazioni in modo tale fornire un servizio best effort anche quando privo di connessione sfrutta due funzioni:
1. [[IP forwarding]]: in cui ad ogni pacchetto in ingresso, viene determinato il link di uscita in modo tale che il pacchetto si avvicini alla destinazione.
2. [[Protocollo di routing]]: serve per mantenere le informazioni aggiornate per fornire l'[[IP forwarding]].