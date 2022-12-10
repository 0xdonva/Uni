Un **segmento TCP** è l'insieme di dati che il livello [[Protocollo TCP|TCP]] chiede ti trasferire al livello [[Protocollo IP|IP]].
Ogni segmento TCP contiene:
- *Payload*: dati del byte stream.
- *Header*: metadati e informazioni di controllo.

## Formazione del segmento
![[Pasted image 20221210122529.png]]
- *Source port* (16 bit): numero di porta del mittente.
- *Destination port* (16 bit): numero di porta del destinatario.
- *Sequence number* (32 bit): Numero di sequenza relativo al flusso di byte che si sta trasmettendo.
- *Acknowledgement number* (32 bit): ACK relativo ad un numero di sequenza del flusso di byte che si sta ricevendo.
- *Hlen* (4 bit): lunghezza dell'header TCP.
- *Reserved* (4 bit): per usi futuri.
- *Code bit* (6 bit): scopo e contenuto del segmento.
	- *URG* (urgent): dati segnalati come urgenti dal livello applicativo.
	- *ACK* (acknowledgement): valore del campo acknowledgement è valido.
	- *PSH* (push): il destinatario deve passare i dati all'applicazione immediatamente.
	- *SYN* (synchronize), *FIN*, *RST* (reset): usati per instaurazione, chiusura ed interruzione della connessione.
- *Window size* (16 bit): dimensione della finestra in ricezione (indica il numero di byte che si è disposti ad accettare in ricezione),
- *Checksum* (16 bit): controllo integrità dei dati trasportati nel segmento TCP (del tutto analogo al caso del protocollo UDP).
- *Urgent pointer* (16 bit): puntatore al termine dei dati urgenti.
- *TCP options*: campo opzionale di lunghezza variabile.
- *Zero padding*: per header con lunghezza multipla di 32 bit (se opzioni)