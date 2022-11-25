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