Abbreviazione di __Time of Check to Time of Use__, questi intendono malfunzionamenti causati da problemi di sincronizzazione, tipico problema dei sistemi multiutente e multitasking.
Il tipico scenario che causa problemi di sicurezza è quando un'operazione sensibile può essere effettuata solo in certe condizioni, queste condizioni sono vere durante la verifica ma se diventano false dopo l'operazione può ancora essere fatta.

### Esempio nel mondo reale
Su un sito tipo wikipedia gli utenti possono modificare le pagine web e gli amministratori possono modificare e bloccare le pagine web.
Un utente vuole modificare una pagina web, la quale non è bloccata e consente all'utente di modificarla.
Un amministratore blocca la pagina web dopo che l'autorizzazione è stata concessa ma prima che l'utente abbia modificato la pagina.
L'utente quindi può ancora modificare la pagina dopo il blocco perché gode dell'autorizzazione ottenuta prima.

## Contromisure
La migliore soluzione sarebbe usare delle transazione atomiche non interrompibili, anche se questo non è sempre possibile.
Un'altra soluzione sarebbe quella di ristrutturare la logica del programma in modo da renderlo non vulnerabile a _race condition_, queste soluzioni però dipendono dalla logica applicativa e possono richiedere modifiche complesse al software.