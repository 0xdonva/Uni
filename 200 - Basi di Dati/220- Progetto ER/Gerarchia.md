Si definisce una *gerarchia di specializzazione* il legame logico che esiste tra classe e sottoclassi.
La gerarchia concettuale è il legame logico tra entità padre $E$ ed alcune [[Entità]] figlie $E_1\space E_2\space...E_n$ dove:
- $E$ e' la *generalizzazione* di $E_1\space E_2\space...E_n$.
- $E_1\space E_2\space...E_n$ sono *specializzazioni* di $E$.

## Definizioni
- *t* sta per *totale*: ogni istanza dell'entità padre **deve** fare parte di una delle entità figlie.
- *nt* sta per *non totale*: ogni istanza dell'entità padre **può** fare parte di una delle entità figlie.
- *e* sta per *esclusiva*: ogni istanza dell'entità padre **deve** fare parte di una sola delle entità figlie.
- *ne* sta per *non esclusiva*: ogni istanza dell'entità padre **può** fare parte di una o più entità figlie.

## Ereditarietà delle proprietà
Le proprietà dell'entità padre non devono essere replicate sull'entità figlia in quanti questa le eredita: le proprietà dell'entità padre fanno parte del tipo dell'entità figlia, non è vero il viceversa.

## Uso delle gerarchie
- Scomposizione di entità in sottoclassi.
- Ricomposizione di schemi parziali in uno schema generale.
- Espansione di schemi consolidati per trattare nuovi sotto-problemi.