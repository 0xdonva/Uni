![[Pasted image 20220415123054.png|500]]
### Ridondanza
- Si ripete più volte il fatto che un impiegato percepisce un certo stipendio.
- Si ripete più volte il fatto che un progetto ha un certo budget.
- I valori di progetto e di impiegato si ripetono e quindi non possono singolarmente essere presi come chiave.
- La chiave è `(progetto, impiegato)`: non si hanno ripetizioni.

### Aggiornamento
- Poiché si ripete più volte il fatto che un impiegato percepisce un certo stipendio, se lo stipendio viene aggiornato questo deve essere fatto su tutte le tuple che riguardano un certo impiegato.
- Poiché si ripete più volte che un progetto ha un certo budget, se il budget viene aggiornato lo si deve fare su tutte le tuple che riguardano un certo progetto.

### Cancellazione
- Supponendo che un impiegato lasci l'azienda o non partecipi a progetti rischiano di perdere i dati sui progetti se era l'ultimo impiegato del progetto.
- Analogamente per i dati degli impiegati se un progetto viene eliminato.
- Se la chiave è `(progetto, impiegato)` in entrambi i casi di eliminazione si potrebbe avere valori nulli nella chiave.