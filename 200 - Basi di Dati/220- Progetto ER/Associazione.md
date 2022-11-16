È un fatto che descrive un'azione o una situazione e che stabilisce legami tra istanze di entità.

### La chiave delle associazioni
La [[Chiave]] è sempre composta ed è definita come composizione delle chiavi delle entità partecipanti.
Esempio:
```
	Dipartimento(codice_dip*)
	Docente(cognome*)
	Appartenenza(codice_dip, cognome)
```
Il fatto che la chiave delle associazioni sia la composizione degli identificatori delle entità partecipanti introduce un ==vincolo di integrità==.

**Vincolo di integrità**: ogni valore componente di una chiave di una istanza di associazione deve essere presente come valore chiave di una istanza dell'entità associata.

### Cardinalità delle associazioni
Per cardinalità si intende il numero di volte che una data istanza di entità deve o può partecipare alla associazione:
- **(1,1)**: obbligatoria, una sola volta.
- **(1,n)**: obbligatoria, almeno una volta.
- **(0,1)**: opzionale, una sola volta.
- **(0,n)**: opzionale, n volte.

### Associazioni N:M
##### Associazione molti a molti
%%IMMAGINE%%
Con vincolo: un ingegnere deve partecipare ad almeno un progetto (1,m).
Senza vincolo: ad un progetto possono partecipare ingegneri, ma può esistere anche un progetto senza ingegneri (0,n).

### Associazione 1:1
%%IMMAGINE%%
- Con doppio vincolo: un reparto deve avere un direttore ed il direttore è uno solo (1,1), un direttore deve dirigere uno ed un solo reparto.
- Il vincolo diventerebbe (0,1) se avessimo l'entità "impiegato" al posto dell'entità "direttore".

### Associazione N:1
##### Associazione molti a uno
%%IMMAGINE%%
- Con vincolo: un oggetto può stare su un ripiano, se sta sul ripiano è intero (0,1).
- Senza vincolo: su un ripiano possono stare oggetti, vincolando la partecipazione $n=5$, non più di 5 (0,5).