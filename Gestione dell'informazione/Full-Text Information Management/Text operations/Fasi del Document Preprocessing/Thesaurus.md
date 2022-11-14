La parola _Thesaurus_ (in italiano _tesauro_) deriva dal greco e dal latino e identifica una lista di _parole importanti_ in un certo dominio di conoscenza, per ogni parola contenuta nella lista esiste a sua volta un gruppo di parole collegate come per esempio le variazioni comuni.
Un tesauro può essere costruito:
- Manualmente da esperti.
- Automaticamente: tramite una collezione di documenti oppure unendo tesauri già esistenti.
- Semi-automaticamente: automaticamente ma fatto da esperti.

### Motivi per usare un tesauro
Il vantaggio di utilizzare un tesauro si basa sulla fondamentale idea di avere un _vocabolario controllato_ per indicizzazione e ricerca:
Indicizzazione:
- Normalizzazione dei concetti indicizzati.
- Riduzione del rumore.
- Identificazione dei termini indicizzati con una semantica chiara.

Ricerca:
- Per assistere l'utente nella formulazione di una query corretta.
- Per fornire gerarchie classificate che permettono l'allargamento e il restringimento della risposta della query.

## Componenti di un tesauro
### Thesaurus Index Term
Usato per indicare un concetto che è l'unità semantica di base.
Può essere singole parole, gruppi di parole o frasi, a volte è necessario implementare una _definizione_ o una _spiegazione_ per eliminare le ambiguità, es. `mouse(Topo in inglese), mouse(Elettronica)`.

### Thesaurus Index Term Relationship
Per la maggior parte composto da sinonimi e semi-sinonimi, vengono infatti utilizzate queste sigle: `BT(Termine più ampio), NT(Termine più specifico), RT(Termine correlato)`.