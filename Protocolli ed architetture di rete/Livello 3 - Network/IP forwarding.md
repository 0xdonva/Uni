L'__IP forwarding__ è un meccanismo con cui un [[router]] trasferisce i datagram da un'interfaccia d'ingresso a quella in uscita, viene effettuato da ogni [[router]].
Per inoltrare i pacchetti:
1. L'[[indirizzo IP]] destinazione viene estratto dall'header del datagram.
2. L'[[indirizzo IP]] destinazione è usato come _indice_ nella [[tabella di routing]].

## Caratteristiche
- _Indipendenza dal mittente_: il next-hop routing, tipicamente, non dipende dal mittente del pacchetto o dal cammino che il pacchetto ha attraversato fino a quel momento.
- La [[tabella di routing]] deve contenere un next-hop router per ciascuna destinazione.