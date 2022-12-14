Il **protocollo S/MIME** (**Secure MIME**) è una versione avanzata del *protocollo MIME*.
Il *protocollo MIME* nasce come sostituto a *SMTP* in quanto quest'ultimo riusciva solo a trasmettere messaggi testuali, mentre grazie a *MIME* si potevano trasmettere foto, audio, video, ecc.
Però il tutto poteva essere letto in chiaro intercettando il traffico Internet.
Così venne inventato **S/MIME** nel 1995.
**S/MIME** permette di firmare messaggi trasmessi in chiaro usando comunque il tipo *MIME/multipart*.
La prima parte del messaggio contiene l'oggetto MIME fa firmare digitalmente mentre la seconda parte contiene la firma digitale.
Gli utenti sprovvisti di S/MIME possono comunque leggere il messaggio.

### Certificati
Per validare le chiavi pubbliche S/MIME usa *le classiche catene di certificati X.509*.
Ogni utente deve possedere un certificato, rilasciato da una [[Certification Authority]] pubblica o in-house.

### Problemi
Oltre all'ostacolo di avere un certificato valido, altri ostacoli hanno impedito a S/MIME di diffondersi:
- Aumento della diffusione delle Web mail, richiedendo agli utenti di condividere le chiavi segrete con il server per poter leggere le mail.
- La cifratura impedisce le funzionalità degli analizzatori *anti-malware*, che dovrebbero essere applicati al momento dell'invio prima della cifratura.