Un **generational garbage collector** partiziona l'insieme di oggetti manipolati dal programma in base alla loro "vecchiaia".
L'idea (*euristica*) è che quanto più è vecchio un oggetto tanto è più facile che rimanga in memoria per molto altro tempo.
L'algoritmo esegue dunque controlli di raggiungibilità *più frequentemente* sugli *oggetti giovani* e meno frequentemente sugli oggetti vecchi.