
Gli impieghi di [[Sistemi multi-agente]] sono variegati, anche se l’applicazione più interessante è
in ambito simulativo: è possibile, creando agenti sufficientemente vicini al corrispettivo reale,
simulare interi sistemi naturali, e valutarne l’evoluzione e studiarne le caratteristiche
significative.
Questa applicazione rappresenta una valida alternativa alle simulazioni di tipo analitico.
Nel nostro percorso di studio, per interagire con gli agenti, abbiamo impiegato il software
NetLogo. NetLogo fornisce all’utente un valido supporto grafico che permette di
collocare, mediante un dialetto del CommonLisp, in un mondo virtuale agenti, e di
gestirne il comportamento. Per avere un sistema omogeneo, il piano 2d in cui si visualizza la
simulazione è toroidale, ovvero andando a sinistra si esce da destra e viceversa.
NetLogo gestisce 4 tipologie di agenti, ciascuna con un uso specifico:
● Turtle: i turtle sono gli agenti che si muovono all’interno del mondo, e che possono
ad esempio rappresentare delle formiche, o delle termiti.
● Patches: agenti che compongono il mondo ma non si muovono. Questi agenti
possono creare turtle. Ogni patch è identificata da una coppia di coordinate.
● Link: agenti che collegano due turtle
● Observer: l’utente, l’osservatore del mondo.
NetLogo permette di creare dei “breed” personalizzati degli agenti Turtle e Patches, ed è
possibile fornire loro delle variabili private. Con netlogo, usando poco codice, è possibile
ricreare complessi sistemi naturali simulati, in particolare provvisti di swarm intelligence.
Osservazioni di Laboratorio
Termiti: dal momento che le termiti non interagiscono tra di loro, viene il dubbio che non si
tratti effettivamente di [[Swarm intelligence]] poiché una singola termite può fare il lavoro di tutte
le altre, cosa non vera per le formiche.
Il lavoro di 1000 termiti fatto in un tempo T viene fatto da 10 termiti in un tempo Tx100.
In particolare all’aumento delle termiti, il tempo di raggiungimento del medesimo risultato,
cala. Al variare del gruppo delle termiti, quindi vi è un aumento di efficacia.