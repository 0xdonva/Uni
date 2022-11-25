Il numero di __porta__ è un numero di 16 bit compreso tra 0 e 65535.
Le porte si dividono in tre categorie:
- 0 - 1023 _Well-known ports_: non devono essere usate senza una precedente autorizzazione da [[IANA]], nella maggior parte dei sistemi possono esser usate sola da processi con _privilegi di root_ o simili.
- 1024 - 49151 _Registered ports_: l'uso di queste porte è registrato a beneficio degli utenti della rete, ma non esistono vincoli restrittivi; nella maggior parte dei sistemi possono essere usate da qualsiasi processo.
- 49152 - 65535 _Dynamic or Private ports_: non è applicato alcun controllo per cui possono essere usate liberamente.

## Assegnazione dei numeri di porta
### Modello client-server
1. Numero di porta del _destinatario_ nel pacchetto inviato da client al server corrisponde al numero di porta del servizio richiesto.
2. Numero di porta del _mittente_ nel pacchetto inviato _dal client al server_ corrisponde ad un numero di porta scelto tra quelli non in uso sul client.
3. Numero di porta del _mittente_ nel pacchetto inviato _dal server al client_ corrisponde al numero di porta del servizio richiesto.
4. Numero di porta del _destinatario_ nel pacchetto inviato _dal server al client_ corrisponde al numero di porta indicato dal client nel messaggio precedentemente inviato.