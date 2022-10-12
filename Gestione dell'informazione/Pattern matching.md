Un __pattern__ è un pezzo di testo che ha certe proprietà sintattiche, es. `comput*`.
Il __pattern matching__ permette di effettuare query che approssimativamente abbinano del testo invece che dei [[token]] di parole.

## Matched pattern
Queste query possono essere utilizzate nel meccanismo di composizione come query di base o per formare frasi e query di prossimità.
Questo perché identificano il segmento di testo che soddisfa il _pattern_ specificato.

## Tipi di pattern
### Prefisso
Una stringa che forma l'inizio di una parola di testo: es. `comput* -> computer,computation,...`

### Suffisso
Una stringa che forma la terminazione di una parola di testo: es. `*ters -> computers, painters, ...`

### Substring
Una stringa che appare all'interno di una parola di testo: es. `*tal* -> talk, metallic, ...`

### Intervallo
Una coppia di stringhe che corrispondono a una qualsiasi parola.