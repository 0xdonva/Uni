Sono fatti che descrivono le caratteristiche delle istanze di entità e le caratteristiche delle istanze di associazione.
Le proprietà assumono valori.
Esempio: `Violi ha matricola 148396` oppure `Violi ha nome Matteo`
Il simbolo utilizzato per rappresentare una proprietà è un spillo collegato o a una entità o ad una associazione:
[IMMAGINE]
Le entità e le associazioni devono essere descritte attraverso la aggregazione di proprietà.
L'aggregato delle proprietà definisce il tipo delle istanze.

## Classificazione delle proprietà
- Scalare: semplice, ad un solo valore. [IMMAGINE]
- Multipla: sono ammessi n valori [IMMAGINE]
- Composta: [IMMAGINE]
- Multipla composta: [IMMAGINE]
- Opzionale: è ammessa la non esistenza del valore. [IMMAGINE]
- Totale: viene usata come alternativa alla proprietà opzionale, per la quale bisognerà specificare separatamente dallo schema l'obbligatorietà della presenza di valore.
- Costante: i valori non possono essere cambiati.
- Calcolata: il valore è calcolato con un algoritmo.
- Unica: tutte le istanze della classe hanno un valore diverso.
- Temporali: proprietà modificabili le cui variazioni devono essere memorizzate.
- [[Chiave]]: identifica in modo univoco la singola istanza di entità. [IMMAGINE]

Al loro ingresso e durante la loro creazione i valori devono essere controllati sulla base di ==[[Vincoli]]== definiti in sede di analisi.