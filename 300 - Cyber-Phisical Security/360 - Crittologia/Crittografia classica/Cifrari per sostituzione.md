I **cifrari per sostituzione** prendono spunto dai *cifrari per shifting* come quello di Cesare, ma invece di spostare l'alfabeto di $n$ posizioni, le lettere vengono sostituite a caso.
Oppure può essere usata una "frase" la quale però non deve avere lettere ripetute: $\text{Chiave: XRAYFILMS}$
$$\text{abcdefghijklmnopqrstuvwxyz}\rightarrow\text{XRAYFILMSBCDEGHJKNOPQTUVWZ}$$

L'alfabeto sostitutivo è decisamente più robusto dello *shifting* in quanto in un alfabeto di 26 lettere vi sono $26!$ possibili combinazione e non $25$.
Un attacco di forza bruta richiederebbe migliaia di anni per provare tutte le possibili combinazioni.

## Crittoanalisi dell'alfabeto sostitutivo
Purtroppo, è possibile utilizzare la *conoscenza della lingua* per semplificare il problema della [[crittoanalisi]].
Difatti la debolezza dei cifrari monoalfabetici sta nel fatto che, anche se le lettere vengono cambiate tra di loro, non si può cambiare "l'identità" della lettera:
- Frequenza della lettera.
- Frequenza del bigramma o del trigramma.
- Affinità con altre lettere.
- Repulsione con altre lettere.
- Tendenza alla posizione nella parola.

Oltre alla *sintassi* c'è sempre la *semantica* a favorire il tutto.
Per evitare il problema della crittoanalisi per frequenza sono state inventate varie tecniche:
- [[Nomenclatore]]
- [[Cifrari omofonici]]
- [[Cifrari polialfabetici]]
- [[Cifrari poligrafici]]