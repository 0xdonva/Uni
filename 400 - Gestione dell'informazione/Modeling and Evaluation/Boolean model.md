Il **modello Booleano** è un semplice modello di retrieval basato sulla teoria degli insiemi e sull'algebra booleana.
Le query sono specificate in espressioni booleane che hanno una precisa semantica.
Data la sua semplicità, il modello Booleano è stato il *principale strumento di ricerca commerciale* per 3 decadi.
Purtroppo però il modello Booleano ha dei lati negativi:
- La sua strategia di retrieval (recupero) si basa su un criterio decisionale binario senza alcuna notazione di classificazione a scala, questo impedisce buone prestazione durante il recupero.
- Spesso non è semplice tradurre un'informazione da ricercare in una espressione booleana.

Nonostante questi inconvenienti, il modello booleano è ancora il modello *dominante* nei sistemi di database dei documenti commerciali
Il modello Booleano considera che quel termine indice sia *presente o assente* in un documento.
Quindi assumiamo che i *pesi dei termini indice* siano *binari* e cioè $w_{i,j}\in\{0,1\}$.
Il modello Booleano prevede che ogni documento sia *rilevante* o *non rilevante*, non esiste il concetto di *match parziale*.
La pesatura dei termini indice porta al [[Vector model|modello vettoriale]].