## HDD
### Funzionamento
Per prima cosa si mette in posizione il pettine, viene raggiunto il cilindro richiesto, viene attivata la testa relativa alla traccia, si attende il settore e infine viene effettuata una lettura/scrittura.

### Settore
Il *settore* è l'unità minima di trasferimento, i settori possono essere raggruppati in blocchi (pagine).

### Indirizzo
L'indirizzo di un settore è: `<numero-cilindro>,<numero-traccia>,<numero-settore>`.

### Tempo di servizio
Il tempo di servizio è:
- tempo di *posizionamento* (seek time): $Ts$, viene indicato dal costruttore come tempo medio di spostamento tra due possibili tracce, vengono anche indicati il $Tmax$ ed il $Tmin$.
- tempo di *latenza rotazionale*: $Tr$, è mediamente la meta' del tempo di rotazione.
- tempo di *lettura* (scrittura): $Tb$, dipende dalla dimensione del blocco.
- tempo impiegato dal *controller*: $Tc$, viene indicato dal costruttore
Per la scrittura si usa anche il metodo *read after write* ($2\times Tr$) che ricontrolla dopo un giro.

## SSD
### Letture
- Nessun tempo di ricerca o di latenza rotazionale.
- Tempo di lettura ($Tb$): (pagina da 4KB) $\sim10\mu s$
- Tempo di accesso $=Tq+Tc+Tb$ ($Tq$: tempo di accodamento).
- Tempo di lettura per una pagina da 4KB: $\sim20\mu s$ 

### Scritture
- Scrivere dati è complesso: $\sim200\mu s-1.7ms$
- La pagina deve essere cancellata prima di poter essere riscritta.
- La cancellazione è possibile solo su insiemi di pagine (tipicamente da 32 a 128): $\sim1.5ms$
- Il controller riscrive e riorganizza molti più dati di quelli effettivamente aggiornati (*write amplification*).
- La scrittura impiega 10 volte la lettura.