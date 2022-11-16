La __mediazione incompleta__ si verifica quando vi sono dati sensibili, sulla base dei quali vengono effettuate operazioni critiche (per la sicurezza o per logica dell'applicazione) e i dati sono in una condizione esposta, possono essere modificati dall'utente.

### Esempio nel mondo reale
Su di un sito di e-commerce, l'utente ha la possibilità di scegliere da un listino una certa quantità di oggetti e la modalità di spedizione.
Ordina via web con il seguente link: `http://www.mysite.com/ordini/finale?custID=232&part=55&quantity=20&price=20&shipping=mail&shipcost=12&total=412`
Una semplice possibilità di manomissione è: `http://www.mysite.com/ordini/finale?custID=232&part=55&quantity=20&price=20&shipping=mail&shipcost=12&total=212`

## Contromisure
Per correggere eventuali errori di un sistema già in uso si possono effettuare due operazioni:
- Aggiungere software di controllo lato server per verificare la correttezza dei dati prima, durante e dopo.
- Riprogettare il tipo di input in modo da limitare al minimo i dati forniti all'utente.
- Riprogettare l'applicazione in modo da non esporre mai informazioni sensibili.
