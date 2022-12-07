Un **One time pad** è l'unico strumento di [[Crittografia#Sicurezza incondizionata e computazionale|cifratura incondizionatamente sicuro]].
La chiave è lunga quanto il messaggio quindi senza alcuna ricorrenza.
Mittente e destinatario devono avere una *copia identica* del blocco e usarlo in modo perfettamente *sincronizzato*.
Il One time pad non usa *ripetizione* e quindi non è crittoanalizzabile.
Poiché ogni lettera del messaggio originale è accoppiata ad un numero casuale differente, il testo cifrato risultante è *incondizionatamente sicuro* rispetto agli attacchi linguistici, di ricorrenza, o dizionario.
OTP è incondizionatamente sicuro ammesso che:
1. Il PAD non venga mai riutilizzato.
2. I numeri pseudo-casuali sono statisticamente impredicibili.

## Problemi dell'OTP
La sicurezza dell'OTP si basa sulla effettiva casualità della chiave: se la sequenza è veramente casuale, il crittogramma non è soggetto ad attacchi.
Problematiche di realizzazione:
- Il problema di generare enormi quantità di chiavi effettivamente casuali.
- La complessità della distribuzione a tutti gli interlocutori blocchi sufficientemente lunghi di chiavi per trasmettere tutti i messaggi necessari.
- Protezione del "pad" da copie e furti.