È un tipo di attacco [[DOS]] remoto che invia pacchetti malformati: invia _pacchetti ICMP malformati_ sfruttando un bug del _protocollo IP_ per cui si riusciva a generare pacchetti IP di dimensioni maggiori a 64 KByte.
I sistemi vulnerabili a questo tipo di attacco sono le versioni datate dei sistemi operativi più comuni come Windows, Linux e MacOs.
Consisteva in un invio di _pacchetti ICMP_ `echo request` di dimensione maggiore della massima consentita, in seguito l'attaccante frammentava i pacchetti e la vittima li riassemblava.
Questo causava un errore nella vittima dovuto alla cattiva implementazione dello _stack TCP/IP_ che portava a crash o riavvii della macchina.
Esistono da diverso tempo patch che hanno risolto questo problema.