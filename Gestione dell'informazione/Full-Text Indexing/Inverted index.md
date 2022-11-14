Un __indice invertito__ (o __inverted index/file__) e un meccanismo basato sulle parole per indicizzare una collezione di testi in modo tale da velocizzarne la ricerca.
L'[[Index|indice]] invertito è composto da due elementi: il _vocabolario_ e le _occorrenze_.
Il __vocabolario__ è un gruppo di parole tutte diverse tra loro nei testi, per ogni parola esiste una lista delle posizioni in cui appare la parola nei testi.
Il gruppo che contiene tutte queste liste viene detto __occorrenze__.
Queste posizioni possono riferirsi a parole o caratteri.
Le liste di posizioni di parole semplificano le frasi e le query di prossimità, mentre la posizioni dei caratteri facilita l'accesso diretto alla ricerca tramite [[pattern matching]].
Lo spazio richiesto dal _vocabolario_ è estremamente piccolo: in base alla legge di Heaps, il vocabolario è grande 