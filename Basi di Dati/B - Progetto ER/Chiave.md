Proprietà che identifica in modo univoco la singola istanza di entità:
- Totale (obbligatoria), unica, esplicita.
- Può essere composta.
- Non è modificabile.
 
 ### Tipo della chiave
 Il tipo dell chiave dipende da tanti fattori:
 - Criteri dipendenti dall'entità (es. `Matricola`).
 - Chiave scelta da altre organizzazioni (es. `Codice fiscale`).
 - Uso pregresso in azienda (es. `protocollo 03pt144`).
 - Scelta condizionata da fattori esterni (es. `codice fiscale o matricola?`).
 - Valori progressivi assegnati dal sistema garantendo l'unicità (fortemente sconsigliati).

## Chiave nel modello relazionale di dati
Sottoinsieme degli attributi dello schema che ha la proprietà di unicità e minimalità:
- *Unicità*: non esistono due tuple con chiave uguale.
- *Minimalità*: sottraendo un qualunque attributo alla chiave si perde la proprietà di unicità.

#### Con moltepli chiavi:
Una è definita *chiave primaria* le rimanenti chiavi sono *secondarie (alternative)*.