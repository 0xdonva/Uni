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
#### Signature based
Comportamento basato sull'assuntio