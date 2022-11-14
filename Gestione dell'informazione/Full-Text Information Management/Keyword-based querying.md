Le query che si basano sulle _keyword_ sono le query più utilizzate perché sono intuitive, facili da esprimere e permettono un ranking veloce.
Possiamo dividerle in gruppi:

## Word queries
Sono le query più elementari che si possono formulare in sistema di ricerca in un testo.
L'alfabeto di queste query è diviso in "lettere" e "separatori", e una parola è semplicemente una sequenza di lettere contornate da separatori.
Nei modelli più complessi vengono permessi certi caratteri che non sono lettere e che non devono essere usati come separatori, es. il _-_ nella parola _on-line_.

## Context Queries
Molti sistemi integrano le query di una sola parola con l'abilità di cercare le parole in un contesto dato.
Si può pensare all'utilizzo del contesto come vera e propria vicinanza fisica delle parole nel testo, per questo possiamo dividere queste query in due sottogruppi:

### Phrase queries
È una ricerca di una specifica frase così come viene scritta, oppure può inserire dei delle parole nel mezzo come intercalari o articoli.

### Proximity queries
È una versione più rilassata delle [[#Phrase queries]], in questo caso viene ricercata una frase con una massima distanza tra le parole che l'utente vuole cercare.

## Boolean queries
È l'approccio più vecchio per combinare keyword queries, consiste nell'usare gli operatori booleani: AND, OR, BUT.

