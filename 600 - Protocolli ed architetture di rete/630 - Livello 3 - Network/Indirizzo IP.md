Un __indirizzo [[Protocollo IP|IP]]__ ha dimensione _32 bit_, ed è solitamente rappresentato tramite i valori di ciascuno dei _4 byte_ che lo compongono in notazione decimale, es. `155.185.121.7`.
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
Ad oggi è necessario utilizzare delle architetture più flessibili rispetto alle classi rigide, quindi gli indirizzi non sono considerati in classi fisse ma l'intero spazio di indirizzamento può essere suddiviso in blocchi di dimensioni differenti.
Si usa la notazione __CIDR__ (_Classless Inter-Domain Routing_) dove ciascun insieme di bit del netid è indicato dal suffisso $n$ nella notazione: $a.b.c.d/n$
Gli indirizzi _CIDR_ richiedono l'utilizzo di strutture dati e algoritmi opportuni da utilizzare per consultare in modo efficace le [[Tabella di routing|tabelle di routing]].

## Assegnamento indirizzi IP
Gli _indirizzi IP_ sono indirizzi _logici_, ciascun host deve essere identificato da un indirizzo IP, che può essere assegnato o permanentemente o dinamicamente al momento del boot.
Questo può essere fatto o attraverso la configurazione manuale del file di rete oppure grazie al [[protocollo DHCP]].

## Indirizzi IP speciali
_Indirizzo di rete_ o _network address_: con tutti i bit dell'hostid uguali a 0, es. `128.211.0.0`
_Indirizzo diretto di broadcast_ o _directed broadcast address_: con tutti i bit del hostid uguali a 1, es. `128.211.255.255`
_Limited broadcast address_: tutti i bit uguali a 1, es. `255.255.255.255` questo permette il broadcast sulla rete fisica locale.
_Nessun indirizzo IP_: tutti i bit pari a 0, es. `0.0.0.0`
_Indirizzo di Loopback (localhost)_: è un indirizzo software virtuale senza corrispettivo hardware e senza connessioni di rete `127.0.0.1`

## Reti private e semi-private
Le __reti private__ sono reti di calcolatori in cui nessun pacchetto entra o esce dalla rete, quindi gli indirizzi devono essere univoci solo all'interno della rete privata.
Le __reti semi-private__ sono reti in cui esistono tre tipi di host:
1. _Nessun accesso_: da/a host fuori dalla rete.
2. _Accesso parziale_: host che possono raggiungere ma non sono raggiungibili dall'esterno.
3. _Accesso completo_: pochi host come per esempio il server Web.
Grazie alle reti semi-private, una rete può essere progettata con host visibili da internet (_host pubblici_) e host non visibili (_host privati_).
Gli _host privati_ possono scambiare pacchetti o solo con altri host privati presenti sulla rete o tramite dei [[NAT router]] all'esterno della rete.