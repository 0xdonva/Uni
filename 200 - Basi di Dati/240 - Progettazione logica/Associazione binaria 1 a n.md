### Traduzione standard
![[Pasted image 20220412150004.png|400]]
Se $E_1$ partecipa con cardinalità $(1,1)$ può essere fusa con l'associazione, ottenendo una soluzione a due relazioni.
```
E1(_K1_, A1,B1,K2,AR,BR)
	FK: K2 REFERENCES E2
E2(_K2_,A2,B2)
```
Se $E_1$ partecipa con cardinalità $(0,1)$ la soluzione a due relazioni ha valori nulli in $K2, AR, BR$ per le istanze di $E_1$ che non partecipano all'associazione.
Equivale a:
![[Pasted image 20220412150513.png|400]]
#### attenzione:
In questo caso, poiché la partecipazione di $E_1$ è $(0,1)$ o $(1,1)$, si nota facilmente che ad un dato valore di $K_1$ corrisponde uno e un sol valore di $K_2$, quindi si può dire che $K_1$ implica $K_2$ o, anche, che esiste una dipendenza funzionale da $K_1$ a $K_2$.