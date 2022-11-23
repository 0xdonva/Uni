Fino agli anni '80 c'era il _protocollo EGP_ poi venne sostituito con il __protocollo BGP__ nel 1995 con l'RFC 1771.
Il __Border Gateway Protocol__ è un protocollo complesso, ma fondamentale per il funzionamento dell'Internet, in quanto è il protocollo delle dorsali Internet per muoversi da un AS a un altro AS in modo _completamente decentralizzato_.
Viene utilizzato dagli [[ISP]] e può essere utilizzato come protocollo _intra-AS_ nel caso di [[Autonomous system|AS]] molto grandi.

Utilizza un algoritmo _path vector_, una variante dell'algoritmo distribuito _distance vector protocol_, in cui ogni routing contiene informazioni sull'_intero cammino_ verso la destinazione attraverso gli AS.
Quando un AS riceve un update riguardo un percorso, controlla se il percorso contiene se stesso:
- Se sì, scarta l'update.
- Se no, aggiunge se stesso e, se necessario, propaga il percorso ulteriormente.

## Interconnessioni tra BGP router
Il BGP usa il [[protocollo TCP]] per connettere i _router peer_ sulla porta 179 questo rende la comunicazione più robusta.
I vantaggi del BGP:
- Un AS determina il percorso, e il protocollo garantisce che non vi siano loop.
- Non ci sono refresh periodici frequenti.
- Gli aggiornamenti sono incrementali.
- Le metriche di un AS sono locali e non esposte.