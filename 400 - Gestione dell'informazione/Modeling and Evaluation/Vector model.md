Il **modello vettoriale** assegna ai termini indice dei valori *non binari* nelle query e nei documenti.
Questi pesi dei termini vengono poi usati per calcolare il *grado di [[similarity]]* (somiglianza) tra ogni documento salvato nel sistema e la query dell'utente.
Ordinando poi i documenti ottenuti in ordine decrescente in base al grado di somiglianza, il modello vettoriale prende in considerazione documenti che combaciano solo parzialmente con la query.
L'effetto risultante principale è che l'insieme dei documenti classificati è molto più precisa di una qualsiasi risposta data dal [[Boolean model|modello Booleano]].

Quindi, un documento $d_j$ e una query utente $q$ sono rappresentati come un vettore  $t$-dimensionale.
Il modello vettoriale propone di valutare il grado di similarity del documento $d_j$ in relazione alla query $q$ come una correlazione tra i vettori $\vec{d_j}$ e $\vec{q}$.
La correlazione può essere quantificata come il *coseno dell'angolo* tra i due vettori.
Questo è, quando $|\vec{d_j}|$ e $|\vec{q}|$ sono le norme del vettore documento e query. Il fattore 