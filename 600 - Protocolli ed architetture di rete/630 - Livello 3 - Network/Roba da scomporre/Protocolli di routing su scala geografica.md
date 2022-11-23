## Routing gerarchico
Nella realtà i router di Internet non rappresentano un insieme omogeneo di risorse e non eseguono lo stesso algoritmo di routing.
Questo succede per diversi motivi:
- _Scalabilità_: all'aumentare del numero di router, se tutti dovessero essere considerati per il routing, il costo degli algoritmi di routing diventerebbe proibitivo.
- _Autonomia amministrativa_: un'organizzazione definita "[[Autonomous system]]"  dovrebbe/vorrebbe scegliere autonomamente come amministrare il traffico tra i propri router e le proprie reti.

## Autonomous system per il routing
I router vengono aggregati in regioni o sistemi autonomi, in pratica, un AS è un insieme di nodi e router gestiti da un'unica entità di controllo centrale.
Ciascun AS ha un numero identificativo assegnato da una _authority_ di registrazione Internet (il numero è compreso tra 1 e 64511 il resto sono riservati).
Per il routing all'interno di un AS (_intra-AS_) i router utilizzano qualche _Interior Gateway Protocol_ (_IGP_) dove i router di un AS possono procedere un'informazione completa su tutti gli altri router.
Per il routing verso altri AS (_inter-AS_) viene utilizzato qualche _Exterior Gateway Protocol_ (_BGP_).
Ciascun AS può usare metriche multiple per il routing interno, ma appare come unico AS ad altri AS.

## Politiche di routing
Le politiche di routing sono le regole per decidere come instradare il traffico, ogni AS vuole poter decidere le proprie politiche e potrebbe anche non farle conoscere agli altri AS.

## Protocolli di routing
### Intra-AS
Principali protocolli di routing intra-AS:
- _Routing Information Protocol_ ([[Protocollo RIP|RIP]])
- _Open Shortest Path First_ (OSPF)
- _Enhanced Interior Gateway Routing Protocol_ (EIGRP)

### Inter-AS
Il principale protocollo in uso è il _Border Gateway Protocol_ (BGP), che ad oggi è uno standard de facto.