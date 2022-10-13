__Sinonimo__: due parole si possono definire sinonimi se il significato è sostanzialmente uguale, questa è una relazione binaria, o due parole sono sinonimi o no.
__Simili__: due parole non uguali ma con caratteristiche che si adattano vicendevolmente, rispetto al rapporto di sinonimia la similitudine è più lasca.
Il concetto di __word similarity__, o similitudine tra parole, deve essere separata dal concetto di parentela tra parole.
La word similarity viene usata in molti campi: [[Information Retrieval]],[[Word sense Disambiguation]],...
Esistono due modi per misurare la sinonimia:
1. Misurazioni basate sul path.
2. Misurazioni sul contenuto informativo.

## Misurazioni basate sul path
Due concetti sono simili se sono vicini tra loro nella gerarchia del [[thesaurus]], devono avere un percorso breve.

### Path distance similarity
Basata sul percorso più breve che connette le parole nella tassonomia:
$$\text{sim}_{\text{path-distance}}(c_1,c_2)=\frac{1}{\text{shortest-path}(c_1,c_2)+1}$$
### Wu-Palmer similarity
Basata sulla profondità di uno dei due termini nella tassonomia e dalla parola in comune più vicina:
$$\text{simwu-palmer}(c_1,c_2)=2\times\frac{\text{depth}(\text{LCS}(c_1,c_2))}{(\text{depth}(c_1)+\text{depth}(c_2))}$$
