Una Local Area Network (LAN) è una rete in cui i nodi possono comunicare fra di loro tramite protocollo di livello H2N.
Il protocollo _h2n_ è solitamente implementato all'interno di una scheda adattatrice, conosciuta come _Network Interface Card_ o _[[NIC]]_.
Le LAN che costituiscono gli elementi fondamentali di accesso a Internet sono dette _back end LAN_ e possono essere collegate mediante _backbone LAN_.

### Back end LAN
Le _back end LAN_ realizzano sistemi (dipartimentali) di medie dimensioni, interconnettendo server, dispositivi di storage, computer, ecc.

### Backbone LAN
Le _backbone LAN_ servono per interconnettere diverse back-end Lan e devono garantire: affidabilità e un'elevata capacità di traffico (tipicamente >1 Gbps, più raramente fino a 100 Gbps).

## Topologie per LAN
A seconda dei contesti e dei protocolli impiegati, possiamo individuare diverse topologie di LAN:

### Topologia a bus
È il metodo più semplice di connettere in rete degli host.
Consiste di un singolo cavo (chiamato _dorsale_) che connette in modo lineare tutti gli host.
I messaggi sono inviati a tutti gli host come segnali elettrici e vengono accettati solo dal [[NIC]] dell'host il cui [[Indirizzo MAC]] è contenuto nel segnale di origine.
I dati trasmessi da un host, se non vengono interrotti, viaggiano da un capo all’altro del cavo, rimbalzano e tornano indietro impedendo ad altri host di inviare segnali.
A ciascuna estremità del cavo viene applicato un componente chiamato terminatore che assorbe i dati liberi rendendo disponibile il cavo per l’invio di altri dati (dipende dalle caratteristiche fisiche del mezzo trasmissivo).
Se un cavo viene tagliato o se uno dei capi viene scollegato, e quindi uno o più capi sono privi di terminatore, i dati rimbalzeranno e interromeperanno il normale flusso di dati.

### Topologia ad anello
Gli host sono connessi tramite un unico cavo circolare privo di terminatori, i segnali sono inviati lungo il circuito chiuso passando attraverso ciascun host che funge da ripetitore e ritrasmette il segnale.

### Topologia a stella
Gli host sono connessi a un dispositivo di rete centrale: i messaggi da qualinque mittente a qualunque destinatario sono inviati attraverso tale componente.
La quasi totalità delle reti [[Ethernet]] moderne sono progettate con questa topologia.
Nel caso di interruzione di uno dei cavi di connessione di un host al dispositivo centrale, solo quell'host verrà isolato dalla rete, però in caso di mancato funzionamento del componente centrale saranno interrotte tutte le attività di rete.