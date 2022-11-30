I **cifrari per sostituzione** prendono spunto dai *cifrari per shifting* come quello di Cesare, ma invece di spostare l'alfabeto di $n$ posizioni, le lettere vengono sostituite a caso.
Oppure può essere usata una "frase" la quale però non deve avere lettere ripetute: $\text{Chiave: XRAYFILMS}$
$$\text{abcdefghijklmnopqrstuvwxyz}\rightarrow\text{XRAYFILMSBCDEGHJKNOPQTUVWZ}$$

L'alfabeto sostitutivo è decisamente più robusto dello *shifting* in quanto in un alfabeto di 26 lettere vi sono $26!$ possibili combinazione e non $25$.
Un attacco di forza bruta richiederebbe migliaia di anni per provare tutte le possibili combinazioni.

## Crittoanalisi dell'alfabeto sostitutivo
Purtroppo, è possibile utilizzare la *conoscenza della lingua* per semplificare il problema della [[crittoanalisi]].
