Composto da un insieme di proxy che esaminano il contenuto dei pacchetti a livello applicazione.
_Proxy_: applicazione di rete che agisce da intermediario tra client e server.
Modifica una sessione tra due parti in due sessioni distinte.
È necessario che sia lanciato un processo proxy per ogni applicazione che si vuol far esaminare dal firewall.
Tutto il traffico della rete deve attraversare il firewall per poter funzionare in ingresso ed in uscita alla rete.
Esistono due tipologie:
- _Proxy Firewall_: i pacchetti devono essere indirizzati espressamente al proxy prima di poter essere inoltrati al destinatario
- _Transparent Proxy_: il proxy è trasparente al client, per cui non vi è necessità di configurazioni particolari per inoltrare al proxy.