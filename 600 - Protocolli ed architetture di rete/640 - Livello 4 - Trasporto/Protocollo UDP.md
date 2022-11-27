Abbreviazione di __User Data Protocol__, definito nel RFC 768, è un protocollo di trasporto leggero, ovvero dotato delle funzionalità minime di trasporto, quali:
1. Servizio di [[multiplazione e demultiplazione]]: UDP aggiunge al messaggio proveniente dal livello applicativo il numero di porta del mittente e del destinatario.
2. _Controllo di errore_: UDP include nell'header un campo checksum.
3. _Servizio di consegna non garantito_, ma solo best effort: i pacchetti UDP possono essere persi, duplicati, consegnati senza ordine.
4. _Servizio senza connessione_: non vi è handshaking tra mittente e destinatario, ogni pacchetto UDP è trattato in modo indipendente dagli altri.

## Pacchetto UDP
![[Screenshot 2022-11-25 at 13-03-15 Microsoft PowerPoint - 04-LivelloTrasporto_parte1.pptx - 04-LivelloTrasporto_parte1_bw.pdf.png]]
#### Campi
- Numero di porta del _mittente_ (16 bit).
- Numero di porta del _destinatario_ (16 bit).
- _Lunghezza_ (16 bit): dimensione in byte del pacchetto.
- _Checksum_:
	- Non è detto che tutti i link forniscano un servizio di livello 2 per rilevare errori.
	- Checksum a livello IP limitato all'header del [[IP datagram]].
	- Non c'è recupero dell'errore.
- _Dati_: contiene il messaggio fornito dal livello applicativo.

### Checksum UDP
Il checksum è calcolato sulla base di tre informazioni:
1. _Pseudo-header UDP_
2. _Header UDP_
3. _Payload UDP_
Lo scopo è quello di individuare errori nel pacchetto trasmesso.
Viene calcolato usando il complemento a 1 della somma di tutti i campi dello pseudo-header e del pacchetto UDP.

#### Pseudo-header UDP
Lo _pseudo-header_ è un insieme di informazioni ricavate dall'header del livello 3 e da informazioni "derivate" non presenti esplicitamente nel pacchetto.
![[Pasted image 20221127120346.png]]
- _Zero padding_: dimensione dello pseudo-header.
- _Protocollo_: campo protocollo del [[IP datagram]].
Viene anteposto al pacchetto UDP, non viene trasmesso dal mittente.