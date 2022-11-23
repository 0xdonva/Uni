Definito nel 1988 dal  [RFC 1058](https://datatracker.ietf.org/doc/html/rfc1058).
È il _primo protocollo storico_ per il routing _intra-AS_, utilizzato per molti anni in Internet.
È un protocollo distribuito basato sull'algoritmo [[Distance vector]]: la metrica di costo è il numero di hop e il costo massimo di un percorso è 16 hop.

I router adiacenti possono scambiarsi due tipi di messaggi:
- _RIP advertisement_: ogni messaggio contiene fino a 25 sotto-reti di destinazione all'interno dell'AS con le relative distanze in hop, viene scambiato ogni 30 secondi.
- _RIP request_: quando un router può anche chiedere informazioni sul vettore di distanze dei router adiacenti.

Se un router non riceve messaggi da suo vicino dopo 180 secondi considera il router irraggiungibile, questa informazione viene poi propagata nella rete in modo tale che anche i vicini possano cambiare velocemente le proprie tabelle di routing.

#### Vantaggi
Come ogni algoritmo distribuito di tipo _Distance Vector_, RIP funziona bene per reti _non grandi_, _stabili_ e _veloci_.
Ciascun router comunica ai vicini il percorso migliore misurato in numero di hop.

#### Svantaggi
Nel momento in cui c'è instabilità, il RIP soffre: non c'è una visione unitaria dello stato della rete e sui percorsi migliori, non c'è intrinseca protezione dai loop e c'è il rischio del "count-to-infinity".