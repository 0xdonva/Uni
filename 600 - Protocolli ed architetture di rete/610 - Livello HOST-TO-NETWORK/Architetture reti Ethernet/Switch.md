Gli __switch__ sono dispositivi fisici che implementano funzionalità di _inoltro selettivo dei frame_ (livello 2) e offrono _alte prestazioni_, questo grazie alla tecnica di filtraggio utilizzando gli [[Indirizzo MAC|indirizzi MAC]].
Tipicamente, lo switch è un dispositivo con molte interfacce di rete ed è usato come centro in una [[Rete LAN#Topologia a stella|topologia a stella]].
Quando un [[Frame Ethernet|frame]] deve essere inoltrato su un segmento [[Rete LAN|LAN]], il [[Bridge]] usa il [[Protocollo CSMA-CD]] per trasmettere.

### Vantaggio dello switch
_Isola i domini di collisione_ producendo un aumento del massimo traffico totale gestibile, e non limita il numero degli host, né la copertura geografica.
Può connettere tipi diversi di [[Ethernet]] e quindi è utile nelle reti gerarchiche.
_Trasparente_, ovvero non necessità di alcun cambiamento agli adattatori [[Rete LAN|LAN]] degli host.

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
I [[Frame Ethernet]] destinati ad host dello stesso segmento non sono inoltrati agli altri segmenti della [[Rete LAN]].

### Inoltro
Per sapere qual'è il segmento di [[Rete LAN]] su cui deve essere inoltrato il [[Frame Ethernet]] si usa l'[[Indirizzo MAC]].

## Tipi di comunicazione
### Store-and-forward
Quando un [[Frame Ethernet]] è instradato attraverso un _commutatore store-and-forward_, è raccolto e immagazzinato nella sua totalità prima che il commutatore inizi a trasmetterlo sulla linea di uscita.

### Cut-through
Il [[Frame Ethernet]] è inoltrato dalla porta di input dello switch a quella di output senza aspettare che tutto il frame sia arrivato al commutatore.
È sufficiente che sia giunta la parte del frame contenente l'indirizzo di destinazione e che il canale di uscita sia libero.