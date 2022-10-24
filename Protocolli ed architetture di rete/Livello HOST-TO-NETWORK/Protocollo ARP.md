L'_Address Resolution Protocol_ o più comunemente ARP si occupa di individuare l'[[indirizzo MAC]] di un della stessa [[rete LAN]] di cui si conosce l'[[Indirizzo IP]].
Il protocollo ARP utilizza due tipi di messaggi:
1. __Richiesta__ contenente l'indirizzo IP del destinatario.
2. __Riposta__ contenente il corrispondente [[indirizzo MAC]].
ARP utilizza il broadcast della richiesta.
Per migliorare le prestazione è stata introdotta una _cache ARP_ per ridurre il traffico sulla rete causato dallo scambio di messaggi ARP:
- Ciascun host effettua un caching temporaneo delle risoluzioni IP/MAC nella sua _routing table_.
- Il mittente inserisce nella richiesta la corrispondenza fra il proprio IP e quello MAC.