Un **NIDS** cattura tutto il traffico di rete utilizzando interfacce in modalità "promiscua".
Tenta di individuare gli attacchi cercando attività sospette nel traffico intercettato.
Per fare questo *distribuisce i sensori* in luoghi strategici della rete, *ispeziona il traffico di rete* e *monitora le attività* degli utenti.
Il problema è che è *incapace* di *analizzare il traffico cifrato*, parti di dati e qualche informazione degli header information potrebbero essere crittografati con [[Protocollo SSL|SSL]] o [[IPSec]].

### NIDS in modalità stealth
Un NIDS è un dispositivo di rete e come tale è soggetto a potenziali attacchi, per configurarlo in modalità stealth si usano:
- Due interfacce di rete:
	1. Una per monitorare.
	2. Una per inviare alert.
- Interfaccia di monitoring senza indirizzo IP.

## Attacchi al NIDS
- [[DOS]] per esaurire le risorse del sistema o approfittarsi degli IDS troppo reattivi in modo da creare tanti falsi positivi.
- *Insertion attack*.
- *Evasion attack*.

## Vantaggi
- Rilevano attacchi che richiedono la manipolazione a basso livello dei pacchetti di rete.
- Possono metter in correlazione attacchi rivolti verso più macchine.
- Non appesantiscono il funzionamento di nessun sistema di produzione.
- Possono rilevare la presenza di [[Worm]]s che si propagano in rete.

## Svantaggi
- Attacchi locali non rilevati.
- Incapacità del reale impatto di un pacchetto.
- Visibilità del traffico in reti switched.
- Proni al flooding massivo.
- Incapacità di analizzare comunicazioni crittografate.