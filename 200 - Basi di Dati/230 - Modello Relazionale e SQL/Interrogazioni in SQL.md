## Dichiaratività di SQL
In [[SQL]] l'utente specifica **quale** informazione è di suo interesse ma non **come** estrarla dai dati.
Il sistema costruisce una strategia di accesso (*query optimization*).
È l'aspetto più qualificante delle basi di dati relazionali.

## Struttura di SQL
Basata sulla composizione di blocchi:
- `SELECT`
- `FROM`
- `WHERE`
Ogni blocco ha il potere espressivo di una qualunque combinazione di selezioni, proiezioni e join.

Esempio:
Studente 
| MATR | NOME    | CITTA   | C-DIP |
| ---- | ------- | ------- | ----- |
| 123  | Carlo   | Bologna | Inf   |
| 415  | Paola   | Torino  | Inf   |
| 702  | Antonio | Roma    | Log   | 
Esame
| MATR | COD-CORSO | DATA       | VOTO |
| ---- | --------- | ---------- | ---- |
| 123  | 1         | 2014-09-07 | 30   |
| 123  | 2         | 2015-01-08 | 28   |
| 702  | 2         | 2014-09-07 | 20   | 
Corso
| COD-CORSO | TITOLO      | DOCENTE |
| --------- | ----------- | ------- |
| 1         | Matematica  | Barozzi |
| 2         | Informatica | Natali  | 

## Interrogazioni semplici
```sql
SELECT *
FROM STUDENTE

SELECT *
FROM STUDENTE
WHERE C-DIP='Log'
```

### Selezione
```sql
SELECT *
FROM STUDENTE
WHERE NOME='Paola'
```
Il risultato è una tabella (priva di nome) con schema: lo stesso di studente.
Istanze: le tuple di STUDENTE che soddisfano il predicato di selezione.

### Proiezione
```sql
SELECT MATR, CITTA
FROM STUDENTE
```
Il risultato è una tabella (priva di nome) con schema: gli attributi di proiezione.
Istanze: le tuple di STUDENTE ristrette a quegli attributi.

## Blocchi SQL per la modifica
Tre operazioni elementari:
- Cancellazione: `DELETE`
- Inserimento: `INSERT`
- Modifica: `UPDATE`

### Cancellazione
```sql
DELETE FROM STUDENTE WHERE MATR='678678'
```

### Inserimento
```sql
INSERT INTO STUDENTE
VALUES ('456789', 'Giorgio Rossi', 'Bologna', 'Log')
```

### Modifica
```sql
UPDATE ESAME
SET VOTO=30
WHERE DATA=2014-04-01
```

## Interrogazioni complesse
### Query con ordinamento
```sql
SELECT * FROM ORDINE
WHERE IMPORTO < 100000
ORDER BY DATA
```

### Query aggregate
Utilizzano le funzioni aggregate:
- `SUM` sommatoria.
- `AVG` media.
- `MIN` minimo.
- `MAX` massimo.
- `COUNT` cardinalita'.
I `NULL` sono esclusi.

#### Query con massimo
Selezionare l'importo massimo:
```sql
SELECT MAX(IMPORTO) AS MAX-IMP
FROM ORDINE
```

#### Query con sommatoria


#### QUery con raggruppamento
Si aggiungono le clausole:
- `GROUP-BY` raggruppamento.
- `HAVING` selezione dei gruppi.
```sql
SELECT ...
FROM ...
WHERE ...
GROUP BY ...
HAVING ...
```
Attenzione: utilizzando `GROUP-BY` il risultato della `SELECT` e' un unico record per ciascun gruppo.