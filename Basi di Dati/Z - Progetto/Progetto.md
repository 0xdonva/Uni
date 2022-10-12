1. [[#Descrizione della realtà da analizzare]]
2. [[#Glossario]]
3. [[#Schema scheletro]]
4. [[#Progettazione concettuale]]
5. [[#Diagramma ER completo]]
6. [[#Progettazione logica]]
7. [[#Codice SQL]]
8. [[#Vincoli aggiuntivi]]

<div style="page-break-after: always; visibility: hidden"> 
\pagebreak 
</div>

## Descrizione della realtà da analizzare
Si suppone di dover realizzare una base di dati per aiutare una banca, composta da varie filiali.  
Una filiale è identificata dal codice univoco e viene descritta da il Comune, dall'indirizzo, da un numero di fax e uno o due numeri di telefono.  
Ogni filiale ha dei dipendenti, di cui uno è il direttore, identificati dalla loro matricola, riportata tramite codice a barre anche sul badge di ognuno, e sono caratterizzate da nome, cognome, indirizzo, numero di telefono aziendale (obbligatorio), email, ruolo e il numero della filiale in cui lavorano.

I clienti della banca sono i correntisti che aprono uno o più conti correnti, sono identificati dal codice fiscale e sono caratterizzati da nome, cognome, indirizzo, email, data di nascita, luogo di nascita, sesso e IBAN dei conti aperti.

La banca vuole tener traccia dei movimenti dei conti correnti aperti presso di loro.  
I conti corrente, oltre ad essere identificati da un IBAN e caratterizzati dal numero di conto relativo alla filiale, data di apertura, data di chiusura e il saldo, appartengono ad una singola persona.  
Con un conto corrente si possono avere una o più carte di credito legate al conto che sono identificate numero di carta di credito, e sono caratterizzate da una data di scadenza e dal CVV.

Le operazioni che possono essere effettuate sui conti sono due:
-   Prelievo/versamento: in cui un correntista effettua questa operazione su un conto.
-   Bonifico: in cui un correntista effettua una transazione da un conto ad un altro.

Il prelievo/versamento, anche detto un "movimento", avviene tramite l'ausilio di una carta di credito, in cui viene rilevato l'importo e la data del movimento.  
Data una data e il numero di conto corrente si può identificare il movimento.  
Il bonifico invece è identificato dal CRO, e caratterizzato dalla data, dalla causale e dallo stato del bonifico.  
Un bonifico è effettuato da un cliente e lega due conti corrente, uno è il mittente e l'altro è il destinatario.

<div style="page-break-after: always; visibility: hidden"> 
\pagebreak 
</div>

## Glossario
| Nome           | Descrizione                                                                                               | Sinonimi    | Legame                                |
| -------------- | --------------------------------------------------------------------------------------------------------- | ----------- | ------------------------------------- |
| Cliente        | CF, Nome, Cognome, Indirizzo, Sesso, Data di nascita, Luogo di nascita, Email                             | Correntisti | Conto corrente, Carta, Bonifico       |
| Carta          | Numero carta, data di scadenza, CVV                                                                       |             | Conto corrente, Movimento, Cliente    |
| Movimento      | Data                                                                                                      |      Prelievo, Versamento       | Conto corrente, Carta                 |
| Conto corrente | IBAN, Saldo, Data di apertura, Data di chiusura                                                           |             | Bonifico, Cliente, Movimento, Filiale |
| Bonifico       | CRO, Data, Causale, Importo, Stato                                                                        |             | Conto corrente, Cliente               |
| Filiale        | Codice, Indirizzo, Telefono, Fax, Comune                                                                  |             | Conto corrente, Dipendente            |
| Dipendente     | CF, Nome, Cognome, Indirizzo, Sesso, Data di nascita, Luogo di nascita, Email, Matricola, Telefono, Ruolo |             | Filiale                                      |

<div style="page-break-after: always; visibility: hidden"> 
\pagebreak 
</div>

## Schema scheletro
![[Pasted image 20220611160115.png]]

<div style="page-break-after: always; visibility: hidden"> 
\pagebreak 
</div>

## Progettazione Concettuale
```
Si suppone di dover realizzare una base di dati per aiutare una banca, composta da varie filiali.  
Una filiale è identificata dal codice univoco e viene descritta da il Comune, dall'indirizzo, da un numero di fax e uno o due numeri di telefono.  
Ogni filiale ha dei dipendenti, di cui uno è il direttore, identificati dalla loro matricola, riportata tramite codice a barre anche sul badge di ognuno, e sono caratterizzate da nome, cognome, indirizzo, numero di telefono aziendale (obbligatorio), email, ruolo e il numero della filiale in cui lavorano.
```
![[Pasted image 20220604172902.png]]
Ogni **Filiale** è riconosciuta grazie ad un codice che consiste in sei caratteri alfanumerici: i primi due sono gli identificativi della provincia di appartenenza mentre i restanti quattro sono numerici, esempio: `MO0001` per la prima filiale di Modena.
Mentre l'identificativo *Matricola* del **Dipendente** è un identificativo numerico valido in tutta la nazione.
L'associazione **Appartiene** ha cardinalità *(1,n)* perché un **Dipendente** può lavora in una e una sola **Filiale** mentre una **Filiale** ha da *1* a *n* dipendenti.

<div style="page-break-after: always; visibility: hidden"> 
\pagebreak 
</div>

```
I clienti della banca sono i correntisti che aprono uno o più conti correnti, sono identificati dal codice fiscale e sono caratterizzati da nome, cognome, indirizzo, email, data di nascita, luogo di nascita, sesso e IBAN dei conti aperti.
```
![[Cliente.jpg|300]]
Tutti questi attributi, a parte *Indirizzo* e *Email*, servono per confermare che il Codice fiscale(*CF*) sia valido.
![[Pasted image 20220604175738.png|200]]
In questo caso l'idea è stata di optare per una generalizzazione delle due entità **Cliente** e **Dipendente** in un'entità padre chiamata **Persona**, la quale raccoglie gli attributi comuni.
![[Pasted image 20220611162416.png]] 
Questa auto-associazione *Gerarchia* permette di capire da chi viene coordinato un dipendente di una filiale.

```
La banca vuole tener traccia dei movimenti dei conti correnti aperti presso di loro.  
I conti corrente, oltre ad essere identificati da un IBAN e caratterizzati dal numero di conto relativo alla filiale, data di apertura, data di chiusura e il saldo, appartengono ad una singola persona.  
Con un conto corrente si possono avere una o più carte di credito legate al conto che sono identificate numero di carta di credito, e sono caratterizzate da una data di scadenza e dal CVV.
```
![[Pasted image 20220604174152.png]]
Il **Cliente**, come specificato in questa immagine, può possedere più **Conti correnti** ma ogni **Conto corrente** è collegato in maniera univoca ad uno ed un solo **Cliente**.
L'entità **Conto corrente**, come spiegato dalla traccia, tra i suoi attributi ha come chiave primaria l'*IBAN* (*I*nternational *B*ank *A*ccount *N*umber): è un identificato internazionale per riconoscere conti bancari all'interno dei circuiti nazionali e segue lo standard ISO 13616:2020.
L'entità **Carta** è l'abbreviazione di **Carta di debito**, il quale è l'unico tipo di carta rilasciato da la banca che ha commissionato il lavoro in quanto la carta di debito, e non di credito, è il tipo più utilizzato in Italia con il 78,8%.
Quest'ultima ha come chiave primaria *Numero carta* che è una stringa di sedici numeri che identificano univocamente la carta a livello internazionale come da standard ISO/IEC 7812.
Una **Carta** può avere un solo possessore il quale verrà impresso sulla carta fisica.

<div style="page-break-after: always; visibility: hidden"> 
\pagebreak 
</div>

```
Le operazioni che possono essere effettuate sui conti sono due:
-   Prelievo/versamento: in cui un correntista effettua questa operazione su un conto.
-   Bonifico: in cui un correntista effettua una transazione da un conto ad un altro.

Il prelievo/versamento, anche detto un "movimento", avviene tramite l'ausilio di una carta di credito, in cui viene rilevato l'importo e la data del movimento.  
Data una data e il numero di conto corrente si può identificare il movimento.  
Il bonifico invece è identificato dal CRO, e caratterizzato dalla data, dalla causale e dallo stato del bonifico.  
Un bonifico è effettuato da un cliente e lega due conti corrente, uno è il mittente e l'altro è il destinatario.
```

![[Pasted image 20220604174946.png|550]]
L'entità **Bonifico** possiede cinque attributi:
- *CRO*: codice identificativo di 11 cifre che identifica una transazione bancaria, segue lo standard ISO 9362.
- *Data*: contiene la data della transazione precisa ai secondi.
- *Importo*: importo transitante, non negativo.
- *Stato*: il possibile stato del bonifico, sono quattro possibili: (In corso), (Inviato), (Annullato), (Rifiutato).
- *Causale*: testo breve legato al bonifico.

Mentre **Movimento** ha solo due attributi: uno è *Importo* che non dev'essere negativo o superare il saldo del **Conto corrente**, l'altro è *Data* che dev'essere preciso al secondo perché insieme all'*IBAN* sono chiavi esterne composte.

## Diagramma ER completo
![[Pasted image 20220708112810.png]]

<div style="page-break-after: always; visibility: hidden"> 
\pagebreak 
</div>

## Codice SQL

### Creazione tabelle
#### Creazione tabella cliente
```sql
CREATE TABLE CLIENTE 
( 
	CF CHAR(16) NOT NULL, 
	Nome VARCHAR(30) NOT NULL, 
	Cognome VARCHAR(30) NOT NULL, 
	Citta VARCHAR(30) NOT NULL, 
	Via VARCHAR(30) NOT NULL, 
	Cap INTEGER NOT NULL, 
	Luogo_Nascita VARCHAR(30) NOT NULL, 
	Data_Nascita DATE NOT NULL, 
	Email VARCHAR(50) NOT NULL UNIQUE, 
	Sesso CHAR(1) NOT NULL, 
	
	PRIMARY KEY(CF), 
	CHECK (LENGTH(CF) = 16), 
	CHECK (Sesso = 'M' or Sesso = 'F') 
);
```

#### Creazione tabella filiale
```sql
CREATE TABLE FILIALE 
( 
	Codice VARCHAR(6) NOT NULL, 
	Citta VARCHAR(30) NOT NULL, 
	Via VARCHAR(30) NOT NULL, 
	Cap INTEGER NOT NULL, 
	Telefono VARCHAR(15) NOT NULL UNIQUE, 
	Fax VARCHAR(25) NOT NULL UNIQUE, 
	Comune VARCHAR(30) NOT NULL, 
	
	PRIMARY KEY(Codice) 
);
```

<div style="page-break-after: always; visibility: hidden"> 
\pagebreak 
</div>

#### Creazione tabella dipendente
```sql
CREATE TABLE DIPENDENTE 
( 
	Matricola INTEGER NOT NULL, 
	CF CHAR(16) NOT NULL, 
	Nome VARCHAR(30) NOT NULL, 
	Cognome VARCHAR(30) NOT NULL, 
	Citta VARCHAR(30) NOT NULL, 
	Via VARCHAR(50) NOT NULL, 
	Cap INTEGER NOT NULL, 
	Luogo_Nascita VARCHAR(30) NOT NULL, 
	Data_Nascita DATE NOT NULL, 
	Sesso CHAR(1) NOT NULL, 
	Ruolo VARCHAR(10), 
	Telefono VARCHAR(15) NOT NULL UNIQUE, 
	Codice INTEGER NOT NULL, 
	
	PRIMARY KEY(Matricola), 
	FOREIGN KEY(Codice) REFERENCES FILIALE(Codice) ON DELETE CASCADE ON UPDATE CASCADE, 
	CHECK (LENGTH(CF) = 16), 
	CHECK (Sesso = 'M' or Sesso = 'F')
);
```

#### Creazione tabella Gerarchia
```sql
CREATE TABLE GERARCHIA 
( 
	Matr_Coordinatore INTEGER NOT NULL, 
	Matr_Coordinato INTEGER NOT NULL, 
	
	PRIMARY KEY(Matr_Coordinatore, Matr_Coordinato), 
	FOREIGN KEY(Matr_Coordinatore) REFERENCES DIPENDENTE(Matricola) ON DELETE CASCADE ON UPDATE CASCADE, 
	FOREIGN KEY(Matr_Coordinato) REFERENCES DIPENDENTE(Matricola) ON DELETE CASCADE ON UPDATE CASCADE 
);
```

<div style="page-break-after: always; visibility: hidden"> 
\pagebreak 
</div>

#### Creazione tabella Conto corrente
```sql
CREATE TABLE CONTO_CORRENTE 
( 
	IBAN VARCHAR(27) NOT NULL, 
	Saldo MONEY, 
	Data_Apertura DATE NOT NULL, 
	Data_Chiusura DATE, 
	CF CHAR(16) NOT NULL, 
	Codice INTEGER NOT NULL, 
	
	PRIMARY KEY(IBAN), 
	FOREIGN KEY(CF) REFERENCES CLIENTE(CF) ON DELETE CASCADE ON UPDATE CASCADE,
	FOREIGN KEY(Codice) REFERENCES FILIALE(Codice) ON DELETE CASCADE ON UPDATE CASCADE 
);
```

#### Creazione tabella Carta
```sql
CREATE TABLE CARTA 
( 
	Numero VARCHAR(16) NOT NULL, 
	Data_Scadenza DATE NOT NULL, 
	CVV INT NOT NULL, 
	CF CHAR(16) NOT NULL, 
	IBAN VARCHAR(27) NOT NULL, 
	
	PRIMARY KEY(Numero), 
	FOREIGN KEY(CF) REFERENCES CLIENTE(CF) ON DELETE CASCADE ON UPDATE CASCADE,
	FOREIGN KEY(IBAN) REFERENCES CONTO_CORRENTE(IBAN) ON DELETE CASCADE ON UPDATE CASCADE 
);
```

#### Creazione tabella Movimento
```sql
CREATE TABLE MOVIMENTO 
( 
	IBAN VARCHAR(27) NOT NULL, 
	Data TIMESTAMP NOT NULL UNIQUE, 
	Importo MONEY NOT NULL, 
	Numero VARCHAR(16) NOT NULL, 
	
	PRIMARY KEY(IBAN, Data), 
	FOREIGN KEY(IBAN) REFERENCES CONTO_CORRENTE(IBAN) ON DELETE CASCADE ON UPDATE CASCADE, 
	FOREIGN KEY(Numero) REFERENCES CARTA(Numero) ON DELETE CASCADE ON UPDATE CASCADE, 
	CHECK (Importo > '0') 
);
```

#### Creazione tabella Bonifico
```sql
CREATE TABLE BONIFICO 
( 
	CRO INTEGER NOT NULL, 
	Data DATE NOT NULL UNIQUE, 
	Causale VARCHAR(70), 
	Importo MONEY NOT NULL, 
	Stato VARCHAR(16), 
	CF CHAR(16) NOT NULL, 
	IBAN_Mittente VARCHAR(27) NOT NULL, 
	IBAN_Destinatario VARCHAR(27) NOT NULL, 
	
	PRIMARY KEY(CRO), 
	FOREIGN KEY(CF) REFERENCES CLIENTE(CF) ON DELETE CASCADE ON UPDATE CASCADE, 
	FOREIGN KEY(IBAN_Mittente) REFERENCES CONTO_CORRENTE(IBAN) ON DELETE CASCADE ON UPDATE CASCADE, 
	FOREIGN KEY(IBAN_Destinatario) REFERENCES CONTO_CORRENTE(IBAN) ON DELETE CASCADE ON UPDATE CASCADE,
	CHECK (Importo > '0')
);
```

### Inserimento di esempi nelle tabelle
#### Clienti
```sql
INSERT INTO CLIENTE VALUES ('RSSPLO76S09A944R', 'Paolo', 'Rossi', 'Bologna', 'Via San Domenico 97', '40121', 'Bologna', '1976/11/09', 'rossi.paolo@gmail.com', 'M');
INSERT INTO CLIENTE VALUES ('BNCMRO97D10D969W', 'Mario', 'Bianchi', 'Modena', 'Via dell Aeroporto 12', '41100', 'Genova', '1997/04/10', 'bianchi.mario@gmail.com', 'M'); 
INSERT INTO CLIENTE VALUES ('CGHSDR48E70F205X', 'Sandra', 'Cuoghi', 'Bologna', 'Via Freschi 12', '16100', 'Milano', '1948/05/30', 'cuoghi.sandra@gmail.com', 'F');
INSERT INTO CLIENTE VALUES ('NLILCA03P58F257L', 'Lucia', 'Noli', 'Castelfranco Emilia', 'Viale Marconi 4', '41015', 'Modena', '2003/09/18', 'noli.lucia@gmail.com', 'F'); 
INSERT INTO CLIENTE VALUES ('ZBLLCA00L12F205U', 'Luca', 'Zoboli', 'Modena', 'Viale Leonardo 3', '41100', 'Milano', '2000/07/12', 'zoboli.luca@gmail.com', 'M');
```

#### Filiali
```sql
INSERT INTO FILIALE VALUES ('MO0001', 'Modena', 'Corso Martiri 27', '41100', '059924567', '059924567@fax.tc', 'Modena'); 
INSERT INTO FILIALE VALUES ('BO0001', 'Bologna', 'Via delle Due Torri 409', '40125', '0516232466', '0516232466@fax.tc', 'Bologna'); 
INSERT INTO FILIALE VALUES ('MI0001', 'Milano', 'Via Agnello 46', '20121', '0270121103', '0270121103@fax.tc', 'Milano'); 
INSERT INTO FILIALE VALUES ('MO0027', 'Castelfranco Emilia', 'Via Emilia 31', '41013', '059925845', '059925845@fax.tc', 'Modena'); 
INSERT INTO FILIALE VALUES ('BO0128', 'Castel Maggiore', 'Via Salina 57', '40013', '0517532488', '0517532488@fax.tc', 'Bologna')
```

#### Dipendenti
```sql
INSERT INTO DIPENDENTE VALUES ('357801', 'NRIGCM80E15F257N', 'Giacomo', 'Neri', 'Modena', 'Viale dei Fiori 63', '41100', 'Modena', '1980/05/15', 'M', 'Manager', '3315674831', '000001'); 
INSERT INTO DIPENDENTE VALUES ('457800', 'RNLSNA95T43F257E', 'Sonia', 'Rinaldi', 'Modena', 'Via San Cristoforo 11', '41100', 'Modena', '1995/12/03', 'F', 'Impiegata', '3345682160', '000001'); 
INSERT INTO DIPENDENTE VALUES ('127833', 'RCCCRL70L24F257W', 'Carlo', 'Rocchi', 'Nonantola', 'Via Loda 8', '41012', 'Modena', '1970/07/24', 'M', 'Impiegato', '3394789020', '075917'); 
INSERT INTO DIPENDENTE VALUES ('663090', 'SCCLNZ01R31F205H', 'Lorenzo', 'Sacco', 'Milano', 'Via della Rosa 88', '20120', 'Milano', '2001/10/31', 'M', 'Impiegato', '3336422838', '458732'); 
INSERT INTO DIPENDENTE VALUES ('335643', 'BRLGDA99T48F257L', 'Giada', 'Baraldi', 'Gaggio', 'Via Sebenico 9', '41013', 'Modena', '1999/12/08', 'F', 'Impiegata', '3389778002', '000001'); 
INSERT INTO DIPENDENTE VALUES ('025811', 'LMBLSN83P23F257O', 'Alessandro', 'Lamborghini', 'Milano', 'Via Prati 31', '20122', 'Modena', '1983/09/23', 'M', 'Manager', '3356789238', '458732');
```

#### Gerarchia dipendenti
```sql
INSERT INTO GERARCHIA VALUES ('357801', '457800'); 
INSERT INTO GERARCHIA VALUES ('357801', '335643'); 
INSERT INTO GERARCHIA VALUES ('025811', '663090');
```

#### Conti correnti
```sql
INSERT INTO CONTO_CORRENTE VALUES ('IT99C1234567890123456789012', '456500,78', '2003/02/08', null, 'RSSPLO76S09A944R', '236791'); 
INSERT INTO CONTO_CORRENTE VALUES ('IT88A0306901651000050570131', '34786,25', '2012/08/23', null, 'BNCMRO97D10D969W', '000001'); 
INSERT INTO CONTO_CORRENTE VALUES ('IT33A0507801651000050478244', '17897,03', '1966/09/15', '2007/05/12', 'CGHSDR48E70F205X', '700056'); 
INSERT INTO CONTO_CORRENTE VALUES ('IT67B0987801432000072178994', '807895,67', '2018/11/20', null, 'ZBLLCA00L12F205U', '000001'); 
INSERT INTO CONTO_CORRENTE VALUES ('IT51C0977311498050072111390', '5987,88', '2022/02/11', null, 'NLILCA03P58F257L', '075917');
```

#### Carte
```sql
INSERT INTO CARTA VALUES ('1234567887654321', '2025/07/01', '234', 'RSSPLO76S09A944R', 'IT99C1234567890123456789012'); 
INSERT INTO CARTA VALUES ('7653925609081200', '2023/11/01', '111', 'ZBLLCA00L12F205U', 'IT67B0987801432000072178994'); 
INSERT INTO CARTA VALUES ('6689010078029030', '2027/03/01', '557', 'NLILCA03P58F257L', 'IT51C0977311498050072111390');
```

#### Movimenti
```sql
INSERT INTO MOVIMENTO VALUES ('IT99C1234567890123456789012', CURRENT_TIMESTAMP, '23,78', '1234567887654321'); 
INSERT INTO MOVIMENTO VALUES ('IT51C0977311498050072111390', CURRENT_TIMESTAMP, '73,88', '6689010078029030'); 
INSERT INTO MOVIMENTO VALUES ('IT67B0987801432000072178994', CURRENT_TIMESTAMP, '66,99', '7653925609081200'); 
INSERT INTO MOVIMENTO VALUES ('IT67B0987801432000072178994', CURRENT_TIMESTAMP, '1399,99', '7653925609081200'); 
INSERT INTO MOVIMENTO VALUES ('IT51C0977311498050072111390', CURRENT_TIMESTAMP, '523,99', '6689010078029030'); 
INSERT INTO MOVIMENTO VALUES ('IT51C0977311498050072111390', CURRENT_TIMESTAMP, '15,08', '6689010078029030');
```

#### Bonifici
```sql
INSERT INTO BONIFICO VALUES ('111', '2022/03/30', 'Pagamento Telefono', '700,99', 'Avvenuto', 'NLILCA03P58F257L', 'IT51C0977311498050072111390', 'IT33A0507801651000050478244'); 
INSERT INTO BONIFICO VALUES ('670', '1999/12/22', 'Pagamento', '325,99', 'Avvenuto', 'CGHSDR48E70F205X', 'IT33A0507801651000050478244', 'IT88A0306901651000050570131');
```