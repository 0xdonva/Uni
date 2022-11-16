Si intende per __struttura implicita__ una struttura in cui i dati possono essere generati al momento dell'accesso, anziché essere memorizzati per intero.
Un esempio può essere una [[Lista]] di numeri, l'accesso sequenziale agli elementi di un generico intervallo $[l,l+1,...,m]$ non necessita la memorizzazione esplicita di $n-m+1$ ma solo la conoscenza del valore di partenza e di quello di arrivo.
Questo può comportare un notevole _risparmio di memoria_,
La soluzione poi si genera al caso in cui i numeri da generare sono separati da una quantità fissa $s$, detta _incremento_ o _passo_.