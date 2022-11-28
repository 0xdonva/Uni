La **gestione manuale della memoria** è un metodo utilizzato nel linguaggio C, il compito di gestire la memoria è lasciato al programmatore attraverso le primitive di sistema (`malloc`, `free`,...).
Questo permette di *limitare* grandemente le perdite di performance, questo però la rende soggetta ad errori, anche gravi.

#### Vantaggi
- Le operazioni di allocazione/de-allocazione sono essenzialmente _chiamate al kernel_ e quindi sono eseguite in modo molto efficiente.
- I _pattern di allocazione e de-allocazione_ sono espliciti e dunque possono essere perfettamente ritagliate sulle esigenze dell'applicazione.

#### Svantaggi
- L'_onere della programmazione_.
- Le potenziali _sorgenti di errore_:
	- L'_aritmetica dei puntatori_.
	- *Segmentation fault*: non vengono effettuati controlli sul fatto che la memoria referenziata a seguito di un'operazione sul puntatore sia effettivamente allocata e disponibile al programma.
	- *Dandling reference*: viene deferenziato un puntatore ad un'area di memoria che è già disallocata.
	- *Memory leak*: 