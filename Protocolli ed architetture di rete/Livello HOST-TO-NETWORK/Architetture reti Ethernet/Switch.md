Gli __switch__ sono dispositivi fisici che implementano funzionalità di _inoltro selettivo dei frame_ (livello 2) e offrono _alte prestazioni_, questo grazie alla tecnica di filtraggio utilizzando gli [[Indirizzo MAC|indirizzi MAC]].
Tipicamente, lo switch è un dispositivo con molte interfacce di rete ed è usato come centro in una [[Rete LAN#Topologia a stella|topologia a stella]].
Quando un [[Frame Ethernet|frame]] deve essere inoltrato su un segmento [[Rete LAN|LAN]], il [[bridge]] usa il [[Protocollo CSMA-CD]] per trasmettere.

### Vantaggio dello switch
_Isola i domini di collisione_ producendo un aumento del massimo traffico totale gestibile, e non limita il numero degli host, né la copertura geografica.
Può connettere tipi diversi di [[Ethernet]] e quindi è utile nelle reti gerarchiche.
_Trasparente_, ovvero non necessità di alcun cambiamento agli adattatori [[rete LAN|LAN]] degli host.

## Metodi di filtraggio e inoltro
Gli switch imparano quali host possono essere raggiunti attraverso quali interfacce, mantengono delle _tabelle di filtraggio_ costruite _automaticamente_.
Quando viene ricevuto un [[Frame Ethernet]], lo switch associa la locazione del mittente e la registra nella tabella del filtraggio.
Nel _record_ della tabella di filtraggio sono presenti:
- [[Indirizzo MAC]] dell'host.
- Interfaccia dello switch.
- Time-To-Live (TTL): il periodo di validità delle informazioni memorizzate nella tabella di filtraggio.
I record vecchi nella tabella di filtraggio vengono scaricati.

## Filtraggio e inoltro dei frame
### Filtraggio
I [[frame Ethernet]] destinati ad host dello stesso segmento non sono inoltrati agli altri segmenti della [[rete LAN]].

### Inoltro
Per sapere qual'è il segmento di [[rete LAN]] su cui deve essere inoltrato il [[frame ethernet]] si usa l'[[indirizzo MAC]].

## Tipi di comunicazione
### S