La __steganografia__ è l'arte di proteggere i dati _nascondendoli_, a differenza della [[crittografia]] che mira a manipolare i dati rendendoli in tal modo incomprensibili.
L'obbiettivo della steganografia è quello di nascondere un _messaggio segreto_ dentro un _messaggio contenitore_ dall'aspetto innocuo e fuorviante.

## Steganografia moderna
### Codifica binaria
Due interlocutori possono utilizzare la steganografia per inviarsi messaggi nascosti all'interno di messaggi contenitori chiamati _file di copertura_.
Tipicamente, i file di copertura moderni sono file multimediali, ottenuti:
- Da un processo di conversione analogico-digitale a cui si aggiunge un qualche tipo di rumore.
- Direttamente da file digitali.
Ogni codifica binaria può essere vista come uno strumento di misura più o meno preciso.
In questo tipo di file multimediali è possibile alterare pochi bit senza alterare in modo evidente il contenuto originario.
Quasi tutti i programmi di steganografia moderna si basano su questo concetto, e sfruttano la diffusione di file contenenti una codifica digitale di immagini, video, suoni.
Uno delle tecniche impiegate consiste nel sostituire i _bit meno significativi_ delle immagini digitalizzate con i bit che costituiscono il file segreto.
I _bit meno significativi_ sono infatti assimilabili ai valori meno significativi di una misura, cioè quelli che possono contenere errori di scarso rilievo.