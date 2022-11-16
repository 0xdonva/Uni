## Aspetti avanzati [[SQL]]
- Aspetti avanzati DML
	- Divisione
- Aspetti avanzati DDL
	- Creazione di indici
	- Modifica degli schemi
	- Gestione di viste
	- Autorizzazioni di accesso

### Divisione
L'operazione di divisione, presente in algebra relazionale, non è definita in SQL pertanto le interrogazioni che richiedono tale operatore, come ad esempio: `Selezionare i dati degli ordini che contengono TUTTI i prodotti di prezzo > 100`  devono essere riformulate con una doppia negazione nel seguente modo `Selezionare i dati degli ordini per i quali NON esiste alcun prodotto di prezzo > 100 che NON sia contenuto in essi`.
```sql
SELECT *
FROM ORDINE O
WHERE NOT EXISTS(
	SELECT *
	FROM PRODOTTO P
	WHERE P.PREZZO > 100
	AND NOT EXISTS(
		SELECT *
		FROM DETTAGLIO D
		WHERE D.COD-PROD = P.COD-PROD
		AND D.COD-ORD = O.COD-ORD))
```

### Creazione di indici
*Indici*: meccanismo di accesso efficiente ai dati.
```sql
CREATE INDEX

CREATE INDEX DATA-IX
ON ORDINI(DATA)
```
```sql
CREATE UNIQUE INDEX

CREATE UNIQUE INDEX ORD-KEY
ON ORDINI(ORD-COD)
```

### Comandi di modifica degli schemi
Necessari per garantire l'evoluzione della base di dati a fronte di nuove esigenze.
È possibile:
- Creare nuovi oggetti (`CREATE`).
- Modificare oggetti preesistenti (`ALTER`).
- Cancellare oggetti (`DROP`).

### Cancellazione degli oggetti
`DROP` (domini, tabelle, indici, view, asserzioni, procedure, trigger):
- Esempio: `DROP TABLE ORDINI`
Opzioni `RESTRICT` e `CASCADE`:
- `RESTRICT`: impedisce drop se gli oggetti comprendono istanze.
- `CASCADE`: applica drop agli oggetti collegati.

### Viste relazionali
Offrono la "visione" di tabelle virtuali (schemi esterni).
Classificate in:
- Semplici: selezione e proiezione su una sola tabella.
- Complesse.
```sql
CREATE VIEW <NOME> AS <QUERY>
OPPURE
CREATE VIEW <NOME> (<NOME-ATTRIBUTI>) AS <QUERY>
```

### Autorizzazioni d'accesso
*Privatezza*: protezione selettiva della base di dati in modo da garantire l'accesso solo agli utenti autorizzati.
Meccanismi di identificazione dell'utente:
- Quando si collega al sistema informatico.
- Quando accede al DBMS.
Si attribuiscono agli utenti dei privilegi di accesso alle risorse, tramite il comando:
```sql
GRANT <PRIVILEGI> ON <RISORSE> TO <UTENTE>
```
Il creatore di una risorse ha tutti i privilegi.
Spesso l'utente *database administrator* crea l'intera base di dati.
Chi detiene un privilegio può concederlo con `GRANT OPTION`:
```sql
GRANT ALL PRIVILEGES ON ORDINE TO USER1 WITH GRANT OPTION
```
Per revocare i privilegi ad un utente:
```sql
REVOKE <PRIVILEGI> ON <RISORSA> FROM <UTENTE> [CASCADE]
```
