Nel sistema di crittografia pubblica prima che due entità si scambino dati usando la crittografia a chiave pubblica, ciascuno vuol essere sicuro che l'altra parte sia quella che dice di essere.
Un modo per essere sicuro è affidarsi ad una terza parte fidata, detta **Certification Authority** (**CA**) che certifica la connessione ad un host e la sua chiave privata.
Una CA rilascia *certificati* che garantiscono la connessione tra una chiave pubblica e una entità:
- Persona.
- Ruolo.
- Organizzazione.
- Dispositivo hardware, driver.
- Servizio informatico.

### Procedura del rilascio del Certificato digitale
Un host effettua una richiesta alla CA chiamata **Certificate Signing Request** o **CSR** inviando la copia di chiavi e firma la propria identità ID e la propria chiave pubblica con la su chiave privata.
La CA effettua le seguenti azioni:
1. *Verifica la firma dell'host*.
2. *Verifica l'identità dell'host*.
3. *Crea un certificato digitale*.
4. *Firma il certificato digitale*.
5. *Spedisce il certificato firmato*.