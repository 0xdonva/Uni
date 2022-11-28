Un __dizionario__ è un oggetto di tipo _mutable_, è un insieme di associazioni fra _chiavi_ (_key_) e oggetti Python arbitrari (_valori_).
La _rappresentazione esterna_ è una sequenza di coppie `<chiave>:<valore>` racchiuse fra parentesi graffe.
L'accesso ad un elemento avviene specificando la _chiave_, per esempio in un dizionario `D` la notazione `D[K]` restituisce il valore associato alla chiave `K`.

## Dict-comprehension
La costruzione dinamica di un dizionario può essere fatta seguendo questa espressione: `{<espressione>:<espressione> for <var> in <iterabile> {if <condition>}}`, esempio:
```jupyter
L = [x:x**2 for x in range(10)]; L
```
