Il **protocollo TCP** (**Transmission Control Protocol**) rispetto a [[Protocollo UDP|UDP]] aggiunge:
- Garanzie di comunicazioni *affidabili*.
- Offre un paradigma di comunicazione *orientato alla connessione* e allo scambio di un *flusso di dati*.

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

#### Rimediare
Ogni trasmissione andata a buon fine vine notificata (*acknowledged*) dall'host ricevente.
Se l'host mittente non riceve un acknowledgement entro l'intervallo di tempo predefinito (*time-out*), il mittente ritrasmette i dati.

### Orientato alla connessione
Un protocollo orientato alla connessione ha tre fasi:
1. *Apertura* della connessione.
2. *Utilizzo* della connessione.
3. *Chiusura* della connessione.

### Orientato allo scambio di un flusso di dati
Il TCP offre un'interfaccia per comunicare e non un semplice scambio di pacchetti.
Per quanto riguarda il *flusso di dati*, il protocollo accetta come input una quantità di dati arbitraria da inviare, non ci sono limiti del pacchetto [[Protocollo IP|IP]] o per vial del protocollo H2N.
TCP implementa la logica di **segmentazione** del flusso di dati in pacchetti: il flusso di dati viene separato in *segmenti*, i quali cono blocchi di dati che TCP invia a IP per costruire il pacchetto.