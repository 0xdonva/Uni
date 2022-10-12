Non sempre i valori delle proprietà possono evolvere liberamente ma sono vincolati da regole.
I vincoli non vengono rappresentati graficamente ma su specifiche a parte.
Esistono due tipi di vincoli:

### Vincoli statici
Viene controllato l'appartenenza di un valore ad un preciso dominio:
- Composizione di stringhe di caratteri: `T1berio no, Tiberio si`.
- Composizione di codici: `AX12300 no, AB123CD si`.
- Verifiche all'interno di intervalli: `18<eta'<65`.
- Presenza di valori in elenchi: `colore in (rosso, verde, bianco,...)`.
Il controllo può essere importante sia in fase di caricamento dati, sia in fase di interrogazione, sia in fase di aggiornamento.
Il vincolo su una proprietà può essere dipendente da valori di altre proprietà.

### Vincoli dinamici
Il controllo statico può non essere sufficiente, un nuovo valore può essere valido staticamente ma può violare la regola in futuro.
