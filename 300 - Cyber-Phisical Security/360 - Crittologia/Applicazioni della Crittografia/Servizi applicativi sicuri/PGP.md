**PGP** è un programma di crittografia a chiave asimmetrica ideato da Philip Zimmermann sul finire degli anni '80.
*Standard de facto* per la crittografia della posta elettronica privata e non solo, valida alternativa al [[protocollo S-MIME]].
Procedura completa:
1. Applica un algoritmo di hashing per generare l'hash del messaggio. L'hash è *firmato* con la chiave asimmetrica privata del mittente e il certificato è allegato al messaggio.
2. Applica l'algoritmo di compressione ZIP per comprimere l'insieme del messaggio e della firma digitale.
3. Genera una chiave simmetrica di 128 bit *random* mediante un algoritmo di generazione di numeri pseudo-casuali.
4. Applica un algoritmo di cifratura simmetrica per codificare il messaggio usando come chiave il numero casuale generato in precedenza.
5. Applica la chiave pubblica da destinatario per cifrare la chiave simmetrica IDEA.
6. Applica l'algoritmo ASCII Armor Radix-64 per trasformare il messaggio in una serie di caratteri ASCII bassi. Ciascun gruppo di tre byte è convertito in un gruppo di 4 byte.