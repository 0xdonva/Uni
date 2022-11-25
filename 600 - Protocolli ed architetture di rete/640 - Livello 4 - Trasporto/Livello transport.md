Il __livello trasporto__ estende il servizio di consegna con impegno proprio del [[protocollo IP]] tra due host terminali ad un servizio di consegna a due _processi applicativi_ in esecuzione sugli host.
I servizi aggiuntivi minimi rispetto a IP sono:
- [[Multiplazione e demultiplazione]] messaggi tra _processi_.
- Rilevamento dell'errore (mediante checksum).
I protocolli _transport_ standard dello stack TCP/IP:
- [[Protocollo UDP|UDP]].
- [[Protocollo TCP|TCP]].
Potrebbero esistere altri protocolli trasporto in contesti particolari e/o proprietari.
L'univocità di ciascun flusso a livello trasporto in Internet è dato dalla quintupla $$[(\text{indirizzo IP}_{x},\text{porta}_{w}),(\text{indirizzo IP}_{y},\text{porta}_{z}),<\text{protocollo trasporto}>]$$