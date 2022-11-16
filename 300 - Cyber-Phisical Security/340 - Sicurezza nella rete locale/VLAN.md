Mediante la __VLAN__, gli host possono essere raggruppati "logicamente" in base al dipartimento di appartenenza, al loro tipo di applicazioni, alle funzioni, al livello di riservatezza, ecc.
Questo la rende nettamente migliore della semplice LAN perché questa a problemi per quanto riguarda i dati confidenziali, i quali viaggiano nella LAN sotto gli occhi di tutti.
Tecnicamente, una __VLAN__ equivale alla creazione di un _dominio di broadcast_:
- Gli host che si trovano all'interno di una VLAN possono comunicare direttamente.
- Gli host che si trovano in VLAN differenti possono comunicare mediante l'intermediazione di un dispositivo di rete.
Una VLAN _segmenta logicamente_ gli host in sottoreti differenti, ciascuna VLAN è realizzata mediante porte di switching private.
Il traffico può essere distribuito tra VLAN differenti mediante router che implementano policy con specifiche "_access list_".

## Realizzare una VLAN
Gli host possono essere aggregati in VLAN tramite soluzioni software basate su:
- Numero di porta.
- Indirizzo MAC.
- Indirizzo IP.
- Tipo di protocollo.
È possibile realizzare VLAN mediante configurazione statica o dinamica.