Il **protocollo TCP** (**Transmission Control Protocol**) rispetto a [[Protocollo UDP|UDP]] aggiunge:
- Garanzie di comunicazioni *affidabili*.
- Offre un paradigma di comunicazione orientato alla *connessione* e allo scambio di un *flusso di dati*.

### Affidabilità
Il livello di *inaffidabilità* del canale di comunicazione determina la complessità del protocollo che deve gestire tale inaffidabilità.
Quindi per creare un canale di comunicazione "virtuale" affidabile serve:
- Capacità di *rilevare* un problema di trasferimento.
- Capacità di *rimediare* in caso di errore.

#### Rilevare
L'uso di *checksum* permette di garantire integrità rispetto a *errori di trasmissione*, è necessario per introdurre ulteriori meccanismi per rilevare altri possibili problemi, che dipendono dal paradigma di comunicazione:
- *Perdite*.
- *Duplicati*.
- *Consegne non in ordine*.