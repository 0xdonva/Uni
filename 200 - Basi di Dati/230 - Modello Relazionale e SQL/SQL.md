## Composizione di SQL
- Data Definition Language ([[Linguaggi|DDL]]): definizione di domini, tabelle, indici, viste,vincoli, procedure, trigger.
- Data Manipulation Language (DML): linguaggi di query, modifica, comandi transazionali.
- Data Control Language (DCL): linguaggio per la gestione degli utenti e dei privilegi di accesso.

## Tipi di dati in SQL-2
*Stringhe*:
- CHAR (N)
- VARCHAR (N)

*Stringhe di bit(0,1)*:
- BIT (N)
- VARBIT (N)

*Numerici esatti*:
- NUMERIC (Prec, Scale) (o anche Decimal)
- INTEGER
- SMALLINT

*Numeri approssimati*:
- REAL
- DOUBLE PRECISION

*Domini speciali*:
- DATE: YYYY-MM-DD
- TIME (N): HH:MM:SS.NNNN
- TIMESTAMP: YYYY-MM-DD HH:MM:SS
- INTERVAL: INTERVAL YEAR(2) TO MONTH (tra 0 anni - 0 mesi e 99 anni - 11 mesi)

### Il valore null
*null* è un valore polimorfo (che appartiene a tutti i domini) col significato di valore non noto.
Il valore esiste in realtà ma è ignoto al database oppure il valore è inapplicabile.

## Definizione delle tabelle
Una tabella è costituita da:
- una lista di uno o più attributi (colonne).
- un insieme di zero o più vincoli.
```sql
CREATE TABLE <nome-tabella>
(<nome-colonna> <dominio> [<vincoli-colonna>],
 ...
 <nome-colonna> <dominio> [<vincoli-colonna>],
 [<vincoli-tabella>]
 )
 ```

### Vincoli di colonna
- NOT NULL: l'attributo non può assumere il valore null.
- UNIQUE: unicità dell'attributo.
- PRIMARY KEY: l'attributo è la chiave primaria.
- CHECK: esprime un generico vincolo sulla colonna tramite una espressione logico-relazionale.
- REFERENCES: esprime il vincolo della Foreign Key.

### Vincoli di tabella
- `UNIQUE (<lista-colonne>)`: la combinazione dei valore delle colonne deve essere unica per tutte le tuple della tabella.
- `PRIMARY KEY(<lista-colonne>)`: chiave primaria della tabella (implica NOT NULL).
- `FOREIGN KEY (<lista-colonne>) REFERENCES <tab> [(<lista-colonne>)]`: foreign key.
- `CHECK (<condizione>)`: predicato che deve essere soddisfatto per tutte le tuple della tabella.

Esempio:
```sql
CREATE TABLE STUDENTE
( MATR CHAR(6) PRIMARY KEY,
  NOME VARCHAR(30) NOT NULL,
  CITTA VARCHAR(20),
  C-DIP CHAR(3)
)
```

### Chiavi alternativa
Per esprimere una chiave alternativa vanno specificate le clausole `NOT NULL` e `UNIQUE`
```sql
CREATE TABLE STUDENTE
( MATR CHAR(6) PRIMARY KEY,
  CF CHAR(16) NOT NULL UNIQUE
  NOME VARCHAR(30) NOT NULL,
  CITTA VARCHAR(20),
  C-DIP CHAR(3)
)
```
CF in questo caso.