**Cliente**(<u>CF</u>, Nome, Cognome, Indirizzo, Luogo_Nascita, Email, Data_Nascita, Sesso)

**Filiale**(<u>Codice</u>, Indirizzo, Telefono, Fax, Comune)

**Dipendente**(<u>Matricola</u>, CF, Nome, Cognome, Indirizzo, Luogo_Nascita, Data_Nascita, Sesso, Ruolo, Telefono, Codice)
	AK: CF
	FK: Codice References Filiale

**Gerarchia**(<u>Matr_Coordinatore</u>, <u>Matr_Coordinato</u>) 
	FK: Matr_Coordinatore References Dipendente 
	FK: Matr_Coordinato References Dipendente 

**Conto_Corrente**(<u>IBAN</u>, Saldo, Data Apertura, Data Chiusura, CF, Codice_Filiale) 
	FK: CF References Cliente 
	FK: Codice_Filiale References Filiale 

**Carta**(<u>Numero</u>, Data_Scadenza, CVV, CF, IBAN) 
	FK: CF References Cliente 
	FK: IBAN References Conto_Corrente 

**Movimento**(<u>Numero</u>, <u>IBAN</u>, <u>Data</u>, Importo) 
	FK: Numero References Carta 
	FK: IBAN References Conto_Corrente 

**Bonifico**(<u>CRO</u>, Importo, Data, Causale, Stato, CF, IBAN_Mittente, IBAN_Destinatario) 
	FK: CF References Cliente 
	FK: IBAN_Mittente References Conto_Corrente 
	FK: IBAN_Destinatario References Conto_Corrente
