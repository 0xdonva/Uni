%%Immagine(Progetto logico relazionale - Parte 2  Slide 37)%%
Su entrambi i rami e' bene specificare il ruolo: conviene la soluzione con due relazioni per evitare rindondanze, vincoli ed eccesso di valori nulli.
```
DIPENDENTE(_MATR_,NOME)
SPOSATI(_MOGLIE_,MARITO)
	FK: MOGLIE REFERENCES DIPENDENTE
	FK: MARITO REFERENCES DIPENDENTE
	AK: MARITO
```
