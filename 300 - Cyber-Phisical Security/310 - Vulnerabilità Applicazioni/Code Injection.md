Questo attacco consiste nell'iniettare codice arbitrario in una applicazione sfruttando il mancato controllo dell'input.
Esistono numerose tecniche che sono _strettamente dipendenti_ dalla tecnologia utilizzata per implementare la logica applicativa.

### Esempio nel mondo reale
Un'applicazione web come Twitter accetta brevi messaggi dagli utenti.
Ciascun messaggio è salvato su di un file che viene interpretato dal server.
Se un attacker inserisce un codice malevolo potrebbe rompere il sistema.

## Contromisure
Per risolvere questa vulnerabilità l'unica soluzione è validare sempre tutti gli input perché ogni input esterno è imprevedibile e potenzialmente dannoso quindi, occorre verificare le dimensioni, il contenuto, il tipo, ...