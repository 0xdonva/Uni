Acronimo di __Open Short Path First__, nato nel 1989, definito nel RCF 1131.
Ha varie funzione migliorative rispetto al [[Protocollo RIP|RIP]] e quindi è adatto a reti _più grandi_ e reti il cui stato tende a _cambiare dinamicamente_.

Il routing si basa sull'algoritmo centralizzato _link state_:
- Topologia delle rete e costi noti a ogni nodo.
- Calcola l'albero dei cammini minimi mediante l'_algoritmo di Dijkstra_.
- Memorizza tale albero nel così detto _link state database_ che vien distribuito a tutti i router.
- Invia in broadcast eventuali aggiornamenti di costo con i vicini router all'intero AS (_flooding_).
- I messaggi OSPF viaggiano _direttamente su IP_.
- Il link state database viene inviato periodicamente anche se non cambiato.

Tutto questo fornisce caratteristiche al OSPF quali:
- _Sicurezza_: possibilità si autenticare i messaggi OSPF con algoritmi di crittografia.
- _Percorsi multipli con costo uguale_: possibilità di usare più percorsi per instradare il traffico.
- _Supporto integrato per instradamento unicast e multicast_: