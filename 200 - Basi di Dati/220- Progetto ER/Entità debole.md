Le *entità deboli* sono quelle [[Entità|entità]] che contengono istanze la cui presenza nel sistema è accettata solo se sono presenti determinate istanze di altre entità da cui queste dipendono.
In caso di eliminazione dell'istanza di riferimento le istanze deboli collegate devono essere eliminate.
L'identificatore dell'entità debole deve contenere l'identificatore dell'entità da cui dipende.
Esempio:![[entitadeboli.png|150]]

## Identificatori esterni
Le entità con identificatore esterno sono deboli poiché a tutti i livelli la cancellazione di una entità provoca la cancellazione delle entità deboli collegate.
In altri casi una eliminazione non comporta la cancellazione delle entità collegate, esempio se l'entità debole ha un identificatore alternativo.

## Regole da rispettare
1. Le identificazioni esterne avvengono sempre con associazioni binarie.
2. Una identificazione esterna può coinvolgere una entità che a sua volta è identificata esternamente a patto che non si creino cicli di identificazione.
3. Una identificazione esterna può coinvolgere più entità purché legate da associazioni binarie dove l'entità da identificare partecipa sul lato (1,1).

## Identificazione esterna composta
Per chiarire la regola 3 faremo due esempi:

#### Esempio 1
- Uno stabilimento è suddiviso in aree.
- Per ogni area si assegnano turni di vigilanza notturna per i custodi.
- Ogni area è assegnata ad un solo custode nel rispetto dei turni settimanali che rimangono invariati per lungo tempo.
- Il turno stabilisce per ciascun custode l'area da vigilare in ciascuna notte della settimana.
Ad una prima analisi affrettata potrebbe portare a: ![[Selezione_006.png|200]]
Errore!: un custode non potrebbe custodire la stessa area più di una volta a settimana (anche se questa frase non era nelle specifiche).
Una seconda analisi porta a due identificati:![[Selezione_007.png|200]]
- Il turno diventa un'entità.
- I due identificatori (chiavi) sono alternativi.
- `(matr, notte)` identifica il turno del custode in una notte che si associa `(1,1)` con l'area, l'area si può associare con lo stesso custode purché cambi la notte del turno.
- `(c_area, notte)` identifica il turno dell'area in una notte che si associa `(1,1)` con il custode, il custode si può associare con la stessa area purché cambi la notte del turno.
