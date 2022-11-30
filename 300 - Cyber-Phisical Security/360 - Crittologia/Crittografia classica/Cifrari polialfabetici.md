I **cifrari polialfabetici** sono dei cifrari che per ogni singola lettera utilizzano un alfabeto diverso, riesce ad eliminare l'evidenza delle frequenze caratteristiche delle lettere più popolari.

Esempio: 
Utilizzo quattro alfabeti $A_1,A_2,A_3,A_4$:
- La prima lettera viene cifrata con la prima lettera di $A_1$, la seconda con la prima di $A_2$ e così via, la quinta, di nuovo con $A_1$.

## [[Crittoanalisi]] per cifrari polialfabetici
Passi di crittoanalisi:
1. Identificare la lunghezza della chiave $L$.
2. Suddividere il testo cifrato in $L$ sottotesti.
3. Applicare un algoritmo di crittoanalisi per frequenza ad ogni sottotesto.

### Metodo Kasiski
1. Ricercare *sequenze* di caratteri identici nel testo cifrato.
2. *Calcolare la distanza* $t$ tra gli inizi di queste sequenze.
3. *Identificare* tutte le sequenze identiche nel testo cifrato e calcolare le varia distanze $t_1,t_2,...,t_k$.
4. *Lunghezza chiave*: $L=MCD(t_1,t_2,...,t_k)$
![[Pasted image 20221130171700.png]]