Il protocollo CSMA/CD (_Carrier Sense Multiple Access with Collision Detection_) è un protocollo ad accesso casuale, completamente decentralizzato.
Sostanzialmente:
- Quando un host deve trasmettere: ascolta il canale.
- Quando un host trasmette: invia i dati alla massima velocità consentita dal canale.
- Quando un host rileva una collisione: ritrasmette il frame fino a quando la trasmissione non ha successo (ad ogni intervallo aspetta un periodo di tempo pseudo-casuale).

## Carrier Sense
_Carrier Sense_ tradotto letteralmente vuol dire _rilevazione del portante_ e cioè ogni host che deve trasmettere ascolta il bus e decide di trasmettere solo se lo trova libero.

### Inter Frame Gap
Due frame consecutivi vengono trasmessi distanziati da un tempo che corrisponde alla lunghezza del pacchetto dati più piccolo, questo intervallo è detto _Inter Frame Gap_ o _IFG_.
L'IFG serve per garantire agli host in ascolto sulla [[rete LAN]] di poter distinguere la fine della trasmissione di un frame dall'inizio della trasmissione successiva.
Prima di trasmettere un host deve ascoltare per un tempo pari all'IFG il canale e deve assicurarsi che sia libero

## Multiple Access
_Multiple Access_ o _accessi multipli_ e cioè che nonostante la funzione __carrier sense__, essendo un protocollo decentralizzato, due host potrebbero decidere di trasmettere in contemporanea, questo perchè essendo il tempo di propagazione non nullo due host possono presumere che il canale sia vuoto allo stesso momento.

## Collision Detection
_Collision Detection_ o _rilevamento della collisione_ in caso si verifichi una sovrapposizione di trasmissioni si ha una collisione.
Per rilevare la collisione, ogni host mentre trasmette ascolta il canale e li confronta con quelli trasmessi da lui.
Se viene rilevata una collisione, l'host interrompe la trasmissione.
A seguito di una collisione:
- Ogni host sospende la trasmissione e trasmette un segnale di __jamming__ per avvisare della collisione gli altri host.
- Il segnale di __jamming__ assicura che ogni host rilevi la collisione anche nel caso in cui la collisione sia stata di breve durata.
- Gli host impegnati a trasmettere ripetono il tentativo di trasmissione dopo un periodo di stop determinato dall'algoritmo di [[Binary Exponential Back-off|exponential back-off]].