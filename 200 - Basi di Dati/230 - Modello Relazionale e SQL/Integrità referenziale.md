Esprime un *legame gerarchico* (padre-figlio) fra tabelle.
Alcuni attributi della tabella figlio sono definiti **FOREIGN KEY**.
I valori contenuti nella **FOREIGN KEY** devono essere sempre presenti nella tabella padre.
Espressa come [[SQL#Vincoli di tabella|vincolo di tabella]]:
`FOREIGN KEY (MATR) REFERENCES STUDENTI(MATR)`
Espressa come [[SQL#Vincoli di colonna|vincolo di colonna]]:
`MATR CHAR(6) REFERENCES STUDENTI (MATR)`
