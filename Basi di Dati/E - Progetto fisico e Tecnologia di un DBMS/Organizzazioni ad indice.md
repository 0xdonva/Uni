## Idea di base
Associare ad un file una tabella nella quale l'entrata i-esima memorizza una coppia del tipo ($k_i$,$p_i$) dove:
- $k_i$ è un valore di chiave.
- $p_i$ è un riferimento al record (tupla) con valore di chiave $k_i$.
- L'indice è ordinato: le coppie ($k_i$,$p_i$) sono ordinate in base ai valori di $k$.

...

## Metodo di accesso
Data una chiave $K$:
1. Accesso all'indice.
2. Ricerca della coppia $(K,(b,i))$.
3. Accesso al blocco dati $b$.
4. Accesso alla tupla contenente $K$ (indirizzo $i$).
Le coppie $(K,(b,i))$ vengono collezionate in blocchi ed ordinate, questi blocchi si chiamano foglie dell'indice e sono tra loro collegati da puntatori.
Al di sopra delle foglie si costruisce un'organizzazione ad albero a più livelli di indirizzamento:
- Ogni foglia è rappresentata da una coppia $(K,b)$ nel livello immediatamente superiore ($K$ è il valore minore),
- I blocchi del livello sopra le foglie sono a loro volta rappresentati a livello superiore, e così via fino ad avere un solo blocco chiamato radice.

## Clustered vs Unclustered
L'indice si dice *clustered* se è costruito su un attributo di ordinamento, altrimenti *unclustered*.
Su una relazione si possono costruire un indice clustered e più di un indice unclustered.
L'indice può essere anche multiattributo (multicolonna), ad esempio. `K:<cognome,nome>`.
Nel caso di clausola **UNIQUE** l'indice garantisce la non ripetizione dei valori.
L'indice può essere costruito su attributi con valori ripetuti, in tal caso la coppia $(K,p)$ diventa $(K,(p1,p2,...,pk))$.

## Indici $B^+$ tree
*$B^+$ tree*: l'albero è associato ad un SW di gestione che lo mantiene sempre equilibrato: ogni percorso dalla radice ad una foglia ha sempre la stessa lunghezza $h$, chiamata altezza del $B^+$ tree.
Ogni blocco (nodo) intermedio ha sempre almeno $O+1$ e non più di $2\times O+1$ figli, contiene almeno $O$ e non più di $2\times O$ valori dell'attributo.
La radice può avere da $2$ a non più di $2\times O+1$ valori.
$O$ si chiama *ordine* del $B^+$ tree.
Le foglie sono riempite dal 50 al 100% (valore tipico 69%).

### Prestazioni del $B^+$ tree
Facciamo riferimento a:
- Dimensione del blocco $D$ (es. 4096).
- Dimensione del puntatore $L(p)$ ai nodi intermedi.
- Dimensione $L(k)$ del valore $K$
Con questi valori possiamo calcolare:
- L'ordine $O$.
- Il numero di foglie $NF$.
- L'altezza $H$.

#### Ordine $O$
Consideriamo il vincolo: $2\times O\times L(K)+(2\times O+1)\times L(p)\leq D$ da cui $O=\lfloor(D-L(p))/(2\times(L(k)+L(p))\rfloor$
Esempio:
Con una dimensione $L(k)$ di 10 si ha $O=146$ e 4 byte inutilizzati per nodo.
Con una dimensione $L(k)$ di 40 si ha $O=46$ e 44 byte inutilizzati per nodo.

#### Numero di foglie $NF$
- Dipende dal numero di tuple $NF$ e dal fattore di riempimento medio dei blocchi $=\ln2\simeq 69\%$.
- Ricordiamo che nelle foglie si avranno un numero di $p=NT$ ed un numero di valori $NK$ da cui
$$NF=\lceil(NK\times L(k)+NT\times L(p))/(D\times\ln2)\rceil$$
Esempio:
Con una dimensione $L(k)=10, NT=10^6,NK=10^4$ si ha: $NF=5776$

#### Altezza minima
L'altezza minima $Hmin$ si può ottenere quanto tutti i nodi sono pieni, poiché al penultimo livello sono necessari $NF$ puntatori alle foglie si ha che: $NF\leq(2\times O+1)^{Hmin}$ e quindi $Hmin=1+\lceil\log_{2\times O+1}NF\rceil$

#### Altezza massima
L'altezza minima $Hmax$ si può ottenere quanto tutti i nodi sono pieni per metà e la radice contiene due soli puntatori, poiché al penultimo livello sono necessari $NF$ puntatori alle foglie si ha che: $NF\leq2\times( O+1)^{Hmax-2}$ e quindi $Hmax=2+\lceil\log_{O+1}NF/2\rceil$
