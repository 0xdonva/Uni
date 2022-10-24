Un __agente__ è qualcuno che agisce in nome di qualcun altro, ovvero agenzia. 
Ha uno scopo ben preciso e deve agire su delega, senza però essere controllato da qualcuno.
Nel mondo reale esempio esistono gli agenti di commercio, di viaggio, immobiliari..
Nel Informatica, un agente è un’unità computazionale (un software od un robot, magari) cioè in grado di manipolare informazione. Esso può agire e percepire l’ambiente attorno ad esso, ed ha un comportamenti autonomi, i quali sono almeno in parte legati al esperienza personale. Quindi può interagire con l’ambiente e altri agenti, possedere tendenze, offrire servizi ma anche riprodursi.
L’agente possiede un _set di regole_ e delle _variabili interne_ (lo stato dell’agente) che possono sia essere costanti sia variare durante la sua vita.

Quando si parla di agente , lo si può fare in due modi:
1. __Paradigma debole__:
	- _Autonomia_ decisionale.
	- _Reattività_: percezione e reazione dell’ambiente.
	- _Proattività_: azione orientata verso certi obiettivi.
	- _Abilità sociale_: comunicazione con altri agenti.
2. __Paradigma forte__ (aggiunge al paradigma debole caratteristiche umane):
	- _Conoscenza_.
	- _Intenzioni_.
	- _Scopi ed altre caratteristiche_.
Di un agente è inoltre possibile valutare caratteristiche come:
- la _mobilità_ in un ambiente
- la _veridicità_ cioè la correttezza nella produzione di informazioni
- la _benevolenza_ (l’agente compie azioni corrette dal punto di vista “etico”)
- la _razionalità_ (le azioni dell’agente sono concordi con il suo obiettivo)

In base al loro processo decisionale, gli agenti vengono divisi in:
● Logici (Logic-based) : deduzioni logiche, agenti il cui processo decisionale è
affidato ad una serie di elaborazioni di tipo logico
● Reattivi (Reactive): mappature dirette situazione-azione, l’azione successiva è
generalmente stabilita da un evento che accade (ad esempio, agente reattivo è il
roomba, perché ha una logica del tipo: ho sbattuto contro a un muro, come reagisco?
Mi giro un po’ e continuo a pulire)
● BDI (Belief-desire-intention): gli agenti BDI prendono decisioni sulla base di
strutture dati che sono in essi contenuti, che rappresentano il Belief, il Desire e
l’Intention. Manipolazione di strutture dati che rappresentano aspettative (idee sul
mondo), desideri (motivazioni interne) ed intenzioni (stati deliberativi).
● Layered : gli agenti layered sono costruiti a strati, ciascuno dei quali è più o meno
dotato di capacità cognitive riguardo l’ambiente.
In base alla natura dell’obiettivo, l’agente ha dei diversi comportamenti: si dice riflessivo
se è regolato dalle proprie percezioni interne (ad esempio, se l’agente deve spostare
l’oggetto A, ma ha fame, l’obiettivo diventa il trovare cibo)
mentre si dice teleonomico se è diretto verso un obiettivo esplicito.
Un’ultima distinzione tra agenti è in base al modo in cui l’agente percepisce e rappresenta
il mondo:
● Cognitivi: attingono da una rappresentazione esplicita del mondo e questo gli
consente di elaborare strategie, pianificare il proprio comportamento e prevedere le
conseguenze delle proprie azioni.
● Reattivi: con rappresentazione sub-simbolica del mondo mediante esempio regole.
Possono solo reagire ad eventi, non si attengono a piani prestabiliti.