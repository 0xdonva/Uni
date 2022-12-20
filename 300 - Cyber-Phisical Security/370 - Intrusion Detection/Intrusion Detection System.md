L'*intrusion detection* è il processo di *identificazione* delle attività di intrusione, non include la *prevenzione* delle intrusioni e le possibili *reazioni* ad attività di intrusione.
Questo è necessario per realizzare un meccanismo di protezione multi-livello, perché gli attacchi non arrivano solo dall'esterno e perché registra attacchi e tentativi di attacco.

Un **Intrusion Detection System** (**IDS**) è uno dei tipici strumenti di difesa come la [[crittografia]] e i [[protocolli sicuri]], è un sistema di *rilevazione*,*segnalazione* e *logging* delle attività di intrusione o utilizzo illecito dei dispositivi di rete, sistemi e applicazioni.

Tra le *funzionalità di base* abbiamo:
- *Analisi* del traffico di rete a vari livelli dello stack TCP/IP, dei log di sistema, di altri eventi.
- *Rilevamento* delle attività sospette e/o illegali.
- *Allerta* dei responsabili della sicurezza.
- *Logging* dettagliato delle attività rilevate

Poi un IDS può avere altre funzionalità per esempio diversi tipi di interfaccia, diverse modalità di allerta, ecc.

I due casi di errore in un IDS sono:
- *Falsi positivi*: quando un IDS segnala erroneamente un'intrusione.
- *Falsi negativi*: quando un IDS non segnala un'intrusione.

Gli indicatori di prestazione di un IDS sono:
- L'*accuratezza* di un IDS è compromessa quando tende a segnare erroneamente un'intrusione.
- La *completezza* di un IDS è compromessa quando tende a non rilevare attacchi esistenti.

## Principali tipi di IDS
### Metodi di rilevamento
#### [[Signature based]]
Comportamento basato sull'assunto che gli attacchi possono essere individuati ricercando pattern specifici o sequenze di eventi.

#### [[Statistical analysis]]
Operano definendo il normale comportamento del sistema e cercano le deviazioni sostanziali da esso. Si accetta il principio che gli attacchi sono un sottoinsieme delle anomalie.

### Modalità di analisi
#### Stateless inspection
Capacità di analizzare il singolo pacchetto, ma non una connessione completa.

#### Stateful inspection
Capacità di analizzare il flusso di pacchetti relativi ad una connessione nel loro insieme.

### Reattività
#### Passive analysis
Gli IDS catturano una copia di tutti i pacchetti che vedono passare e li analizzano per cercare di individuare eventuali attacchi o azioni illegali.
L'analisi passiva serve per la rilevazione, non è invadente per il normale funzionamento della rete e non ne peggiora significativamente le prestazioni.
Nel caso vengano rilevati attacchi in corso, vengono loggati.

#### Active analysis
Questi IDS oltre al logging hanno la possibilità di prendere provvedimenti quando rilevano un attacco.
L'obbiettivo è rendere le intrusioni inoffensive quanto prima possibile e limitare gli eventuali danni.

### Localizzazione e tempistiv