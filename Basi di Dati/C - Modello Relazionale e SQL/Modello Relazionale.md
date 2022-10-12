È un modello logico di rappresentazione o strutturazione dei dati di un database implementato su DBMS, detti perciò RDBMS.

## Definizione informale
| MATR | NOME     | CITTA'  | C-DIP |
| ---- | -------- | ------- | ----- |
| 123  | Carlo    | Bologna | Inf   |
| 307  | Giovanni | Milano  | Log   |
| 415  | Paola    | Torino  | Inf   |
| 702  | Antonio  | Roma    | Log   |

## Definizione formale
*Dominio D*: un qualunque insieme di valori.
*Prodotto cartesiano* su n domini (non necessariamente distinti), D1xD2x...xDn: insieme di tutte le n-uple (*tuple*) <d1,d2,...,dn>, con $d_i\in D_i, 1\leq i\leq n$
*Relazione* R su D1,D2,...,Dn: un qualunque sottoinsieme di D1xD2x...xDn.

## Proprietà
*Grado* della relazione: numero di domini (n).
*Cardinalità* della relazione: numero di tuple.
*Attributo*: nome dato ad un dominio in una relazione (i nomi di attributo in una relazione devono essere tutti distinti fra di loro).
*Schema di una relazione*: tabella(attr1,...,attrN).
*Istanza di una relazione*: un insieme di tuple su (attr1,...,attrN).

## Confronto della terminologia
| Definizione Formale | Definizione Informale |
| ------------------- | --------------------- |
| Relazione           | Tabella               |
| Attributo           | Colonna               |
| Tupla, n-upla       | Riga                  |
| Dominio             | Tipo di dato          |
| Cardinalita'        | Numero di righe       |
| Grado               | Numero di colonne     |                    |                       |

