Un insieme di associazioni <nome,[[Dato|oggetto]]> con lo stesso _livello di visibilità_ viene chiamato __namespace__.
Senza considerare le [[Classe|classi]], possiamo dire che in Python, rispetto al punto di vista del _codice in esecuzione_ ad un determinato momento, sono definiti _tre namespace_:
1. _Built-in_: viene creato non appena l'interprete inizia l'esecuzione del programma, esso contiene i nomi di particolari [[Dato|oggetti]] (ad esempio, [[abs]] o [[id]]) che dunque sono noti durante tutta l'esecuzione.
2. _Globale_: ogni modulo di cui è composto un dato programma.
3. _Locale_: spazio riservato ad ogni [[funzione]].
Per comprendere da quale _namespace_ viene risolto un determinato riferimento simbolico, dobbiamo considerare le _regole di visibilità_ (o regola di [[Lexical scoping|scope]]) adottate da Python.

## Manipolazione dei namespace
In Python i namespace, che altro non sono che tabelle associative, sono rappresentati esplicitamente come [[Dizionario|dizionari]].
Sono cioè essi stessi strutture dati e, come tali, possono essere _manipolati dal programma_, al riguardo esistono due funzioni: [[globals]] e [[locals]].