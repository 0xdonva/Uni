![[Pasted image 20221105123217.png]]
Questo è il __Datagram IP__ di un pacchetto [[IP]] versione 4 consiste in questi campi:
- _VERS_: versione del protocollo [[IP]] usata per creare il _datagram_.
- _HLEN_: lunghezza dell'header del _datagram_ (in parole di 32 bit).
- _TOTAL LENGTH_: lunghezza del _datagram_ [[IP]] (in byte), dimensione massima $2^{16}=65536$ byte.
- _TYPE OF SERVICE (TOS)_: campo il cui scopo è stato modificato negli anni: inizialmente doveva includere informazioni per la gestione differenziata dei pacchetti in base a requisiti applicativi, ora invece è un uso misto di funzionalità legate a concetti di _classe di traffico_ e _segnalazione esplicita di congestione_.
- I successivi tre campi dell'header del _datagram_ servono per gestire, quando necessaria la _frammentazione_ e la _ricostruzione_ del datagram:
	1. _IDENTIFICATION_: intero che identifica il datagram.
	2. _FLAGS_: controllo della frammentazione.
	3. _FLAGMENT OFFSET_: la posizione del frammento nel datagram originale.
- _TIME TO LIVE_: non è un vero valore temporale, indica per quanto tempo il datagram può circolare in [[Internet]]. È decrementato da ciascun [[router]] che gestisce il _datagram_.
- _PROTOCOL_: indica quale protocollo applicativo può utilizzare i dati contenuti nel _datagram_.
- _HEADER CHECKSUM_: serve per collegare l'integrità dei dati trasportati dall'header.
- _SOURCE IP ADDRESS_: [[indirizzo IP]] del mittente.
- _DESTINATION IP ADDRESS_: [[indirizzo IP]] del destinatario.
- _IP OPTIONS_: campo opzionale di lunghezza variabile, serve per il testing e il debugging della rete.
- _PADDING_: campo opzionale che serve per fare in modo che l'header abbia lunghezza multipla di 32 bit.