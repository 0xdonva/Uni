Un __indirizzo IP__ ha dimensione _32 bit_, ed è solitamente rappresentato tramite i valori di ciascuno dei _4 byte_ che lo compongono in notazione decimale, es. `155.185.121.7`.
L'indirizzo IP viene usato come identificatore univoco in un servizio di comunicazione universale.

## Componenti dell'indirizzo IP
L'indirizzo IP è composto da 32 bit suddivisi in 4 campi, in cui ciascun campo è formato da un byte e separato da un punto (_dotted notation_).
Ogni indirizzo è solitamente strutturato in una coppia: $$ <\text{netid},\text{hostid}>$$
Dove _netid_ indica la rete e _hostid_ identifica un host di quella rete.
Quello che determina questi due campi o è l'assegnazione di _classi predefinite_ o la ripartizione manuale tramite notazione _classless_.

## Classi di indirizzi IP
Per quanto riguarda le classi di indirizzi esistono tre tipi di classi:
1. Classi utilizzabili per l'indirizzamento di host (_classe A, B e C_).
2. Classe per il multicast address (_classe D_).
3. Classe riservata (_classe E_).

### Dimensioni delle classi
- _Classe A_: 7 bit per netid (128 possibili network), 24 bit per hostid (16 milioni di possibili host).
- _Classe B_: 14 bit per netid (16384 possibili network), 16 bit per hostid (65536 milioni di possibili host).
- _Classe C_: 21 bit per netid (2 milioni di possibili network), 8 bit per hostid (256 possibili host).

## Indirizzi _classless_
