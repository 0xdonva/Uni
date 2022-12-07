Può essere utilizzata per autenticare una qualunque sequenza di simboli binari, indipendentemente dal loro significato.
Permette di applicare il principio di non ripudiabilità: si evita che il firmatario possa negare di aver inviato le informazioni.

## Funzionamento
```
Il mittente cifra un digest del documento con la sua chiave privata (apponendo la sua firma digitale) e poi cifra documento + digest con la chiave pubblica del destinatario.
Il destinatario decifra documento + digest con la sua chiave privata e decifra il digest con la chiave pubblica del mittente.
```
Con questa applicazione, che combina tutte le tecniche, si possono avere: [[Applicazioni della Crittografia|autenticità, integrità e non ripudiabilità]].

### Passi
Bob spedisce un messaggio eseguendo le seguenti operazioni:
1. Sottopone il messaggio $M$ ad hashing e genera un digest di lunghezza fissa.
2. Cifra il digest $D$ con la chiave privata di Bob e allega il risultato $DC$ (digest cifrato) al messaggio.
3. Cifra l'insieme $M+DC$ con al chiave pubblica di Alice.

L'insieme cifrato $M+DC$ arriva ad Alice che esegue le seguenti operazioni:
1. Decifra l'insieme cifrato $M+DC$.
2. Riapplica l'hashing sul messaggio $M$ ed ottiene un nuovo digest.
3. Decifra il digest ricevuto con la chiave pubblica di Bob.
4. Confronta i due digest:
	- Se sono uguali, la firma è autentica e il messaggio non è stato modificato.
	- Se sono diversi, manca l'autenticazione del mittente o l'integrità del messaggio.

### Terze parti fidate
#### Problema 1
Come fanno due entità a stabilire uno scambio di chiavi segrete sulla rete?
	Tramite [[Key Distribution Center]] fidati che agiscono come intermediari.

#### Problema 2
Quando Alice ottiene la chiave pubblica di Bob come può essere sicura che sia la chiave di Bob e non quella di un Attacker?
	Tramite [[Certification Authority]] fidate.