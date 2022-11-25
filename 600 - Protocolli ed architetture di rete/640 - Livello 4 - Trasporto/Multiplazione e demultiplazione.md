Il [[protocollo IP]] non consegna i dati tra processi applicativi in esecuzione sui nodi terminali perché questo è un compito del _protocollo di trasporto_.
La __multiplazione__ è la creazione dei segmenti provenienti dai messaggi di diversi processi applicativi.
La __demultiplazione__ è l'analisi di ogni segmento dello strato trasporto in modo da ottenere l'informazione usata per determinare a quale processo deve essere consegnato il segmento.
[[Protocollo TCP|TCP]] e [[Protocollo UDP|UDP]] attuano la _multiplazione/demultiplazione_ includendo due campi speciali nell'header del segmento:
- Il numero di [[porta]] del mittente.
- Il numero di [[porta]] del destinatario.
Permettono di identificare in modo univoco i due processi applicativi, residenti su due nodi terminali e comunicanti tra loro.