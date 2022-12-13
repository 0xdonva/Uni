Il **protocollo IKE** è composto da due fasi:
1. Autenticazione dell'utente remoto che vuole iniziare una sessione [[IPSec]] e scambio delle chiavi di sessione.
2. Negoziazione dei parametri della *SA IPSec*.

## Fase 1
Due possibili metodi:
1. *Pre-shared key*: utilizzabile con host che non hanno indirizzo IP fisso. Quindi, l'indirizzo IP non può far parte delle informazioni necessarie per l'autenticazione. La sicurezza si basa sulle politiche di gestione delle chiavi.
2. *Certificato digitale*: utilizzabile solo se gli host hanno un indirizzo IP fisso. Un certificato per ogni entità che si connette usando IPSec. Possibilità di amministrazione centralizzata da parte di una [[Certification Authority]].

## Fase 2
I due nodi utilizzano la [[Protocollo ISAKMP|ISAKMP]] per negoziare la SA per altri protocolli.
Caratteristiche delle SA:
- Ogni SA fa riferimento ad un canale unidirezionale.
- Una SA è univocamente determinata da:
	- Protocollo di sicurezza.
	- Indirizzo IP sorgente.
	- Connection ID.