In generale, per maneggiare sistemi complessi, si rivela molto più facile pensare in termini di
collettività piuttosto che singoli individui, in quanto allo stesso modo è impostata la natura
umana (un singolo umano,come un agente, è limitato).
Nei [[Sistemi multi-agente]], è possibile osservare l’emergere della “swarm intelligence”,
traducibile come “intelligenza di sciame”.
E’ la proprietà di un sistema in cui il comportamento collettivo di agenti semplici
produce l'emergere di schemi funzionali globali nel sistema stesso.
Le caratteristiche della swarm intelligence sono generalmente che:

● ogni individuo che compone lo sciame di agenti è tipicamente poco sofisticato e
ha capacità limitate, agiscono in base ad un meccanismo azione-reazione
● ogni individuo del sistema non conosce lo stato globale del sistema;
● nessun elemento del sistema dirige esplicitamente il comportamento globale

Gli swarm systems sono molto adattabili all’ambiente. Essi riescono a reagire a stimoli
ambientali riconfigurando il proprio comportamento.
La swarm intelligence si basa sulle scelte casuali di individui che compongono il sistema. Da
cui deriva uno dei più grandi vantaggi che è la possibilità di adattarsi a qualsiasi situazione
iniziale o cambiamento, il tutto senza rischio di stagnare i minimi locali. Se ne deduce che
nessuna situazione è quella finale ma ci sono sempre alternative che possono essere
esplorate.
Gli swarm systems derivano dai sistemi multi-agente per peculiare filosofia in cui i due
focus principali sono: gruppo e ambiente. L’ambiente è inteso come mezzo di
coordinamento tra gli agenti e non solo come luogo nel quale attingere alle informazioni.
Gli agenti possono comunicare tra di loro in modo diretto oppure attraverso la stigmergia.
La stigmergia è una forma di comunicazione indiretta che avviene alterando lo stato
dell’ambiente in modo tale da influenzare il comportamento degli altri individui, poiché
l’ambiente stesso è uno stimolo per gli altri individui.
Svantaggi
Perdita di una soluzione certa e/o finale ad un problema e nella dispersione di risorse da
parte degli agenti, in attività inutili.

## Esempi
Sincronizzazione: avviene quando sciami di lucciole pulsano tutte allo stesso momento.
Ciascuna lucciola percepisce il grado di illuminazione del proprio ambiente locale.
● Se la luminosità nelle proprie vicinanze è sufficiente ed essa non è ancora
pronta ad emanare luce propria, ricomincia il processo di ricarica.
● Alla pulsazione successiva, la lucciola pulserà in sincronia con le altre.
La sincronizzazione è tanto più efficace quanto più è grande il sistema da
sincronizzare

Aggregazione: fenomeno in cui agenti si “coalizzano” per fare fronte a problemi comuni.
Certe amebe spendono la maggior parte del proprio tempo come singoli individui.
Quando il cibo scarseggia, esse si aggregano in un’unica grande colonia, con
maggiori possibilità di spostamento e di conseguenza di trovare cibo.

Il processo di aggregazione avviene per opera di un feedback positivo. Le singole
amebe cercano e disperdono feromone contemporaneamente formando gruppi detti
cluster, i quali a loro volta più facili a loro volta da “annusare” per amebe non ancora
incluse.
Il fenomeno di aggregazione è limitato dalla evaporazione del feromone
nell’ambiente.
Ant sorting: organizzazione tipica dei nidi di formiche
Le formiche vagano nel nido seguendo direzione casuali, ed annusano
continuamente ciò che li circonda. Esse sono provviste di una piccola memoria a
breve termine e possono ricordare gli oggetti visti nei passi più recenti.
La probabilità che una formica afferri un certo oggetto cala se ne ha già visto
un’altro simile più recentemente.
La probabilità che una formica lasci cadere l’oggetto che trasporta, aumenta se ha
visto altri oggetti dello stesso tipo.
I mucchi che si formano generano feedback sia positivi che negativi, incentivando
le formiche a depositarvi oggetti simili e disincentivandole a sottrarne di già
depositati.
Il sistema funziona indipendentemente dalla struttura del nido e dai cambiamenti
ambientali di sorta.
L’ant sorting è impiegato per riordinare i file in sistemi p2p.
Ant foraging: sistema di caccia delle formiche
Le formiche si allontanano dal cibo in cerca di cibo muovendosi casualmente
nell’ambiente. Quando una formica trova il cibo, ne prende una parte e tornando
verso il nido libera un feromone .
Le altre formiche che intercettano il feromone vengono indirizzate verso il cibo.
La dinamica del feromone naturalmente si incrocia con quella dei movimenti casuali.
Più feromone individua, più cibo trova.
La dinamica del feromone consente robustezza verso i cambiamenti ambientali e
consente di individuare i camini più brevi.
Un’alternativa potrebbe essere l’uso di due feromoni, uno per il cibo, uno per il nido
ed è quella usata nei sistemi artificiali di ant foraging.
L’ant foraging è un’ottima tecnica per la risoluzione di problemi TSP (commesso
viaggiatore) nonché efficace sistema di routing nelle reti. I sistemi P2P beneficiano
dell’ant foraging nella ricerca di informazione nella rete.
Aggiungendo un numero significativo di formiche il compito viene portato a termine molto più
velocemente.