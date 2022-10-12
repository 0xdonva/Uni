A livello [[Ethernet]], gli host utilizzano un _indirizzo MAC_ (_Media Access Control_).
Ad ogni [[NIC]] viene associato un indirizzo LAN __univoco__ di 48 bit, tipicamente rappresentato da sei coppie di numeri esadecimali.
Da standard l'indirizzo di broadcast è _FF:FF:FF:FF:FF:FF_ dove tutti i bit sono a 1.
L'indirizzo MAC di un [[NIC]] è univoco e permanente: l'indirizzo è formato da sei coppie di cui le prime tre solo il _OUI_ (_Organizationally Unique Identifier_) che identificano il produttore del [[NIC]] e gli ultimi tre sono assegnati da produttore che deve rispettare il vincolo di univocità dato dalla IEEE.

## Utilizzo dell'indirizzo MAC
Quando un host vuole trasmettere, inserisce nel frame l'indirizzo MAC del destinatario e lo immette nella LAN.
Se l'indirizzo di destinazione del frame corrisponde all'indirizzo MAC dell'host ricevente, il frame viene accettato e viene passato ai livelli sopra, se no viene scartato (questo a meno che l'host non stia usando un software di sniffing e quindi il [[NIC]] è in modalità _promisqua_).
