Il **modello vettoriale** assegna ai termini indice dei valori *non binari* nelle query e nei documenti.
Questi pesi dei termini vengono poi usati per calcolare il *grado di [[similarity]]* (somiglianza) tra ogni documento salvato nel sistema e la query dell'utente.
Ordinando poi i documenti ottenuti in ordine decrescente in base al grado di somiglianza, il modello vettoriale prende in considerazione documenti che combaciano solo parzialmente con la query.
L'effetto risultante principale è che l'insieme dei documenti classificati è molto più precisa di una qualsiasi risposta data dal [[Boolean model|modello Booleano]].

Quindi, un documento $d_j$ e una query utente $q$ sono rappresentati come un vettore  $t$-dimensionale.
Il modello vettoriale propone di valutare il grado di similarity del documento $d_j$ in relazione alla query $q$ come una correlazione tra i vettori $\vec{d_j}$ e $\vec{q}$.
La correlazione può essere quantificata come il *coseno dell'angolo* tra i due vettori.
Questo è, quando $|\vec{d_j}|$ e $|\vec{q}|$ sono le norme del vettore documento e query. Il fattore $|\vec{q}|$ non influisce sul ranking perché esso è uguale per tutti i documenti.
Il fattore $|\vec{d_j}|$ fornisce una normalizzazione nello spazio dei documenti.
Poiché $w_{i,j}\ge0$ e $w_{i,q}\ge0$, $\text{sim}(d_j,q)$ varia da $0$ a $+1$. Così, invece di tentar di predire se un documento è rilevante o meno, il modello vettoriale classifica i documenti in base al loro grado di somiglianza con la query.
Un documento potrebbe essere recuperato se corrisponde alla query anche solo parzialmente. Si potrebbe stabilire una sogli che accetta solo quelli con un grado di somiglianza superiore alla soglia, ma comunque per calcolare le classifiche è necessario innanzitutto specificare come si ottengono i pesi dei termini indice.
$$\text{sim}(d_j,q)=\frac{\vec{d_j}\bullet\vec{q}}{|\vec{d_j}|\times|\vec{q}|}=\frac{\sum_{i=1}^t{w_{i,j}\times w_{i,q}}}{\sqrt{\sum_{i=1}^t w_{i,j}^2}\times\sqrt{\sum_{j=1}^t w_{i,q}^2}}$$
