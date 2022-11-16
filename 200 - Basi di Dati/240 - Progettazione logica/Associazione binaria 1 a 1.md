### Forma standard
![[Pasted image 20220412151000.png]]
#### Traduzione con una relazione:
`E12(_K1_,A1,K2,A2,AR)`
Se le cardinalità sono entrambe 1 la chiave può essere indifferente $K_1$ o $K_2$ si sceglierà quella più significativa.

Se la cardinalità di $E_2$ è $(0,1)$ e quella di $E_1$ è $(1,1)$ allora la chiave sarà $K_2$. $E_2$ è l'entità con maggior numero di istanze alcune delle quali non si associano, ci saranno quindi valori nulli in corrispondenza di $K_1$, $K_1$ in questo caso non potrebbe essere scelta.

Se la cardinalità è $(0,1)$ da entrambe le parti allora le relazioni saranno due per l'impossibilità di assegnare la chiave all'unica relazione a causa della presenza di valori nulli sia su $K_1$ che su $K_2$.

#### Traduzione con due relazioni:
L'associazione può essere compatta con l'entità che partecipa obbligatoriamente la discussione sulla chiave è analoga al caso di traduzione con una relazione.
```
E1(_K1_,A1)
E2(_K2_,A2,K1,AR)
```

#### traduzione con tre relazioni:
La chiave della relazione che traduce l'associazione può essere indifferentemente $K_1$ o $K_2$, non ci sono problemi di valori nulli.
```
E1(_K1_,A1)
E2(_K2_,A2)
R(_K1_,K2,AR)
```
