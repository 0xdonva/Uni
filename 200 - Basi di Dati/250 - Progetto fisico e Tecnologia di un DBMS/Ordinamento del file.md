Ordinare un file è utile non solo per la presentazione del contenuto, ma anche per velocizzare la ricerca.
L'ordinamento di un file molto grande è un'[[Meccanica del disco|operazione molto lenta]] che viene di regola effettuata con il metodo *Sort/Merge (a M vie)*, supponiamo di avere un file di $NB$ blocchi che non puo' essere contenuto in memoria di lavoro, il file viene ordinato in due fasi:
- La fase di sort.
- La fase di merge.

### Fase di sort
Il primo passo è un sort, dove i blocchi costituenti il file ($NB$) vengono raggruppati in $NF$ file (a gruppi di $NM$) ed ordinati, e successivamente dispersi su $M$ dispositivi logici.

### Fase di merge
La fase è costituita da più passi:
- Vengono portati in memoria gradualmente i blocchi di $M$ file, si opera una fusione ordinata delle tuple contenute ottenendo un file $M$ volte più grande (ordinato).
- L'operazione si ripete fino ad esaurire dli $NF$ file.
I passi si ripetono fondendo file sempre più grandi fino ad ottenere un unico file ordinato.

## Tipi di organizzazione
I tipi di organizzazione sono sostanzialmente due:
- Le [[Organizzazioni ad indice]] che utilizzano file di supporto che riportano per ogni valore della chiave l'indirizzo nel file di dove è localizzata la tupla.
- Le [[Organizzazioni hash]] che per allocare una tupla in un file sottopongono la chiave ad una trasformazione con una funzione detta hash che trasforma il valore della chiave in un valore numerico che corrisponde all'indirizzo nel file.