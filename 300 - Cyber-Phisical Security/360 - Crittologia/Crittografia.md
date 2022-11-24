__Crittografia__: dal greco kriptos (nascosto) e grafein (scrivere).
Arte di progettare _algoritmi_ il cui scopo principale è quello di rendere illeggibile un testo in chiaro a chi non è autorizzato dall'autore, mediante un'operazione nota come cifratura:
- _Testo cifrato_: il testo ottenuto secondo qualche tecnica crittografica, detto anche _crittogramma_.
- _Cifrario_: indica tutto il procedimento utilizzato per ottenere il testo cifrato partendo dal testo in chiaro.
- _Decifrazione_: operazione che riporta nella sua forma in chiaro il testo cifrato.

## Sicurezza incondizionata e computazionale
Uno schema di cifratura è detto _incondizionatamente_ sicuro se il testo cifrato generato _non contiene abbastanza informazioni_ per determinare il testo in chiaro, _indipendentemente da quanto_ testo cifrato sia disponibile.
Con l'eccezione dello schema _one-time pad_, _nessun algoritmo_ di cifratura _è incondizionatamente sicuro_.
Nella pratica, uno schema di cifratura è detto _computazionalmente sicuro_ se rispetta _almeno uno dei due_ elementi su cui si basa la sicurezza:
- Il _costo_ per crittoanalizzare il codice _supera il valore_ dell'informazione cifrata.
- Il _tempo necessario_ per crittoanalizzare il codice _supera il tempo_ per cui l'informazione contenuta è ritenuta utile.

## Tipi di crittografia
- Crittografia _classica_: fino all'avvento delle macchine cifranti, prima dei computer. Si basa sull'utilizzo di una o entrambe le tecniche di _sostituzione_ e di _trasposizione_.
- Crittografia _moderna_: si basa sulle tecniche di sostituzione e di trasposizione ed eventualmente su _algoritmi_ matematici. Tutti sono implementati al computer. Sono divisi in:
	- _Algoritmi simmetrici_ (detti anche a chiave _simmetr_)