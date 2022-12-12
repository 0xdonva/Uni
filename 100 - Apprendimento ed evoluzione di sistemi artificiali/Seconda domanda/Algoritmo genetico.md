Un **algoritmo genetico** è un algoritmo ispirato al principio della selezione naturale ed evoluzione biologica.
L’aggettivo *genetico* è dovuto al fatto che gli algoritmi genetici attuano dei meccanismi concettualmente simili a quelli dei processi biochimici scoperti nella genetica.
Per comprendere meglio questi algoritmi, facciamo un passo indietro:

In natura esistono vari esempi di sistemi capaci di apprendere, cioè modificare sé stessi in risposta a stimoli esterni. Su una scala temporale più ampia, avviene lo stesso per le singole specie (evoluzione biologica).
Parlando di *cambiamento delle specie*, a livello storico esistono *due filoni di pensiero*:
- quello di Lamarck, dove i cambiamenti avvenuti in una vita vengono trasmessi ai discendenti (collo delle giraffe, che si allunga di generazione in generazione) e che porta ad un graduale adattamento della specie all’ambiente.
- secondo invece Darwin e Wallace, i cambiamenti rilevanti nell’evoluzione della specie sono presenti sin dalla nascita, e sono fondamentalmente casuali.

Nel caso di Darwin, l’ambiente esercita una pressione selettiva che favorisce i portatori di caratteri vantaggiosi, e coloro che non li possiedono verranno eliminati, lasciando solo quelli con le caratteristiche migliori.

La pressione selettiva fa si che due specie che occupano lo stesso luogo competono per le stesse risorse ambientali(che sono una risorsa finita), dove a sopravvivere è quella che riesce a crescere più velocemente viceversa ci sarà il caso del estinzione(sopravvivenza del più adatto).

Darwin, pur avendo intuito le caratteristiche dell’evoluzione non ne conosce ilmeccanismo, che viene alla luce in seguito agli esperimenti di Mendel e alle
scoperte di Chargaff che dice che il DNA trasmette l’informazione genetica.

Il DNA è una sequenza di nucleotidi, ognuno dei quali contiene una base azotata
● A-Adenina
● C-Citosina
● G-Gunina
● T-Timina

Il cambiamento Darwiniano, avviene per
● Mutazioni puntiformi: modifiche casuali e puntuali nella sequenza nucleotidica di un
gene.

● Duplicazione dei geni: divergenza delle coppie dei cromosomi omologhi durante la
meiosi
● Ricombinazione cromosomica: il cosiddetto “crossing over”, cioè lo scambio di
porzioni omologhe di materiale genetico durante la meiosi
Evoluzione ed apprendimento sono molto simili tra loro, in quanto nel corso
dell’evoluzione una specie apprende implicitamente le caratteristiche stabili dell’ambiente in
cui vive. L’apprendimento può essere visto come anche un processo di generazione di
diversi comportamenti e di selezione di quelli che sono i più adatti.
Definizione: Fitness di un individuo è definita come il numero di discendenti fertili.
Applicato al modello matematico visto sopra, questo discorso fa capire che è la popolazione
con fitness più alta ad avere il sopravvento nell’accesso e nell’uso delle risorse.
Si possono usare tutte queste proprietà viste fin’ora per poter generare i cosiddetti
“Algoritmi Genetici”. Si avranno in particolare:
● Una popolazione iniziale di individui differenti
● Un sistema di valutazione per ciascun individuo
● Un meccanismo stocastico per generare nuovi individui, partendo da quelli già
presenti con fitness più elevata
● Un meccanismo che introduca novità nei nuovi individui, mantenendoli comunque mediamente più simili ai genitori che agli altri individui.

### Esempio
Un insieme di soluzioni è detta popolazione, m stringhe binarie a ciascuna delle quali è
associato un valore di fitness ovvero il numero di discendenti fertili. Applicato il modello
matematico secondo il quale “sopravvive” il più forte, riusciamo a capire che è la
popolazione con fitness più alta ad avere il sopravvento nell’accesso e nell’uso delle
risorse.
Le stringhe binarie rappresentano cromosomi, e i geni che li compongono codificano una
determinata proteina, che vanno quindi a determinare il “corpo” dell’individuo.
Per risolvere i problemi imitando la selezione naturale, si valutano gli individui della
popolazione corrente, si trovano i più adatti, li si ricombina, li si muta e si dà origine ad una
nuova popolazione, e il processo si ripete.
La scelta dei genitori proporzionale al fitness (ogni individuo ha una probabilità di essere
scelto) è quella più vicina alla metafora biologica, ma presenta svantaggi:
● La ricombinazione (crossover) di due individui che portano , può generare individui
molto migliori di entrambi, con fitness simili oppure relativamente scadenti. Questa
procedura però, non è in grado di creare un tratto se non è presente in nessuno dei
due genitori.
● Per questo si introduce la mutazione, che può seguire due metodi:

● con una certa probabilità ogni nuovo individuo originato dal crossover viene
mutato in una posizione casuale
● oppure prendo un genitore e lo muto sicuramente

La fitness media cresce con le iterazioni, e tende a raggiungere quella dell’individuo
migliore, anche se questo non accade in natura. Quando la fitness media si avvicina
sufficientemente alla fitness del migliore, l’algoritmo può essere arrestato.

Se non ci fosse crossover, gli schemi migliori si replicherebbero, ma non ci sarebbe la
componente che crea novità. In generale, la popolazione tende a convergere verso una
situazione in cui tutti si somigliano, e questo porta a fenomeni di convergenza prematura
(una popolazione non ottimale colonizza tutto), il che arresta il progresso.
Per controllare questo fenomeno, è necessario poter valutare e controllare i tempi di
convergenza.

## Tecniche per il rallentamento della convergenza
### Strategia delle nicchie
Una strategia è quella di immaginare un sistema composto da vari sottoinsiemi collocati
in punti diversi dello spazio(nicchie), e che la genetica abbia luogo all’interno di
ciascuno di essi. Alcuni individui con fitness elevata possono generare figli nelle nicchie
limitrofe, ad una certa frequenza.

Per rappresentare il concetto nelle nicchie possiamo immaginare un toro di celle quadrate,
diviso in macchie colorate, che corrispondono a diversi schemi, o sottopopolazioni.

La riproduzione di individui con fitness alta può avvenire in tutte le 8 celle limitrofe.

La colonizzazione dello spazio da parte degli individui più forti necessita tempo, per cui
viene data la possibilità a zone più lontane di sviluppare alternative, che possono talvolta
rivelarsi vincenti.

## Tecniche di scelta dei genitori
### Elitismo e Scaling
La scelta proporzionale alla fitness, è quella più fedele alla biologia. Pone però due effetti
collaterali negativi: la possibile scomparsa di individui molto performanti e la possibile
convergenza prematura, se un individuo è molto superiore alla media.
Le alternative a questo sistema sono:
● Elitismo: si garantisce la sopravvivenza degli individui con fitness più alta,
copiandoli semplicemente. Questo non rallenta la convergenza prematura, ma evita
la perdita di soluzioni valide.(Copia gli individui migliori della generazione precedente
senza applicarvi mutazioni o crossover, permettendo di evitare la perdita di individui
con alto fitness a causa della casualità)
● Scaling: selezione non dipendente in maniera lineare dalla fitness. Aumenta o
diminuisce in favore dei più adatti. In sostanza, la probabilità che un esemplare sia
scelto non è proporzionale alla fitness, ma è funzione di essa(la probabilità di essere
selezionato non è proporzionale alla fitness, ma ad una funzione correlata)

### Selezione per rango
Si ordinano gli individui per fitness decrescente, poi si assegnano punteggi decrescenti
secondo una distribuzione arbitraria(es. punteggi nelle corse formula 1). Il vantaggio è che
non dà convergenza prematura e non subisce mutamenti nella distribuzione dei punteggi.
E’ però pesante dal punto di vista computazionale e non corrisponde alla realtà biologica.

### Scelta per torneo
Si estraggono a caso un certo numero di individui da una popolazione(uno stesso individuo
può essere scelto più volte). Tra questi, l’individuo designato per la riproduzione è quello con
fitness più alta. Si itera questo procedimento per un certo numero di volte.

La scelta per torneo ha una convergenza molto meno rapida della soluzione proporzionale,
di fatto sostituendola in molti casi.
Variante degli algoritmi genetici
Il crossover tende a distruggere combinazioni di building blocks lontani. Le possibili
soluzioni sono due
1. il crossover a due punti
2. il crossover uniforme

Gli Algoritmi Genetici originali sono codificati in forma binaria. Esiste la possibilità di usarne
forme discrete (alfabeti da k>2 simboli), oppure a numeri reali. In questo caso, si deve
modificare l’operatore di mutazione.

## Ottimizzazione
Gli Algoritmi Genetici possono essere usati per cercare il valore massimo di una data
funzione. Essendo il sistema stocastico, non è vincolato a cadere in un estremo locale.
Non vi sono richieste di proprietà particolari da imporre alla funzione da ottimizzare. E’
sufficiente disporre di un metodo per valutare la fitness di ogni soluzione proposta.
Il metodo è particolarmente efficace quando il crossover non genera troppe soluzioni illegali,
quando le posizioni dei massimi sono correlate, o quando è sufficiente una approssimazione
di una soluzione.
In generale, gli GA possono localizzare una regione con fitness elevate, ma la convergenza
verso un valore molto preciso non è particolarmente veloce. In questo caso, serve
appoggiarsi a metodi risolutivi supplementari.

## Applicazioni
Utilizzando diversi tipo di GA e operatori, sono nate applicazioni in vari settori, tra cui
problemi classici, problemi di scheduling, ottimizzazione funzioni, image processing, bin
packing, machine learning ...