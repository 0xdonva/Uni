I concetti fondamentali della **applicazione della [[crittografia]]** sono:
- *Riservatezza*: certezza che la comunicazione inviata non sia intercettabile e violabile da qualcuno.
- *Integrità dei dati*: certezza che in nessun punto la comunicazione sia stata modificata.
- *Autenticazione*: certezza della "identità" mittente.
- *Non ripudio*: impossibilità del mittente di negare di aver trasmesso.

La combinazione delle due chiavi (privata e pubblica) oltre all'hashing permettono di poter esprimere al meglio le potenzialità della crittografia.
Obbiettivo tipico della crittografia è quello di garantire:
- *Segretezza del documento*.
- *Autenticità del documento*.
- *Integrità del documento*.

### Segretezza del documento
```
Il mittente cifra il documento con la chiave pubblica del destinatario.
Il destinatario decifra il documento con la propria chiave privata.
```
Questa applicazione garantisce la *segretezza* del documento ma non la sua *autenticità*, poiché chiunque potrebbe aver utilizzato la chiave pubblica del destinatario.

### Autenticità del documento
```
Il mittente cifra il documento con la sua chiave privata.
Il destinatario decifra il documento con la propria chiave pubblica del mittente.
```
Questa applicazione garantisce la *autenticità* del documento ma non la sua *segretezza*, poiché chiunque intercetti il messaggio potrebbe decifrare il messaggio.