# Descrizione della realtà da analizzare
Si suppone di dover realizzare una base di dati per aiutare una banca, composta da varie filiali.
Una filiale è identificata dal numero univoco e viene descritta da il Comune, dall'indirizzo, da un numero di fax e uno o due numeri di telefono.
Ogni filiale ha dei dipendenti, di cui uno è il direttore, identificati dalla loro matricola, riportata tramite codice a barre anche sul badge di ognuno, e sono caratterizzate da nome, cognome, indirizzo, numero di telefono aziendale (obbligatorio), numero di telefono personale (opzionale), email, ruolo e il numero della filiale in cui lavorano.

I clienti della banca sono i correntisti che aprono uno o più conti correnti, sono identificati dal codice fiscale e sono caratterizzati da nome, cognome, indirizzo,  email, data di nascita, luogo di nascita, sesso e IBAN dei conti aperti.

La banca vuole tener traccia dei movimenti dei conti correnti aperti presso di loro.
I conti corrente, oltre ad essere identificati da un IBAN e caratterizzati dal numero di conto relativo alla filiale, data di apertura e data di chiusura, appartengono ad una singola persona.
Con un conto corrente si possono avere una o più carte di credito legate al conto che sono identificate numero di carta di credito, e sono caratterizzate da una data di scadenza e dal CVV.

Le operazioni che possono essere effettuate sui conti sono due:
- Prelievo/versamento: in cui un correntista effettua questa operazione su un conto.
- Bonifico: in cui un correntista effettua una transazione da un conto ad un altro.

Il prelievo/versamento, anche detto un "movimento", avviene tramite l'ausilio di una carta di credito, in cui viene rilevato l'importo e la data del movimento.
Data una data e il numero di conto corrente si può identificare il movimento, ma anche data la data e il numero di carta di credito.
Il bonifico invece è identificato dal CRO, e caratterizzato dalla data, dalla causale e dallo stato del bonifico.
Un bonifico è effettuato da un cliente e lega due conti corrente, uno è il mittente e l'altro è il destinatario.