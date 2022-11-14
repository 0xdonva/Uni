Una seconda opzione diversa dalle [[structural querying]] è quello di costruire una struttura dati sopra al testo, chiama __indice__ (o __index__) per velocizzare la ricerca.
È molto utile l'indicizzazione quando si parla di grossi e semi-statici testi, quest'ultime sono collezioni di testi che possono essere aggiornate a intervalli regolari.

## Tecniche di indicizzazione
Dovendo considerare il costo della ricerca, lo spazio di overhead e il costo di costruzione e aggiornamento della struttura possiamo avere tre tecniche:
1. [[Inverted index]].
2. [[Suffix arrays]].
3. [[Signature files]].