Con l'avanzamento delle tecniche di difesa, gli attacchi dei professionisti stanno diventando sempre più sofisticati, mascherati e persistenti nel tempo.
Questa è una tipologia di attacchi che riguardano soprattutto le aziende medio-gradi in quanto sono attacchi con _investimenti alti_ per un'organizzazione, quindi si attacca chi può garantire un ritorno dell'investimento.
Gli APT sono tipicamente organizzazioni para-statali, ma possono anche essere organizzazioni criminali che mettono a disposizione le proprie competenze.

## Passi dell'attacco
1. __Ricognizione__: gli attaccanti cercano e identificano gli obbiettivi che verranno attaccati nell'attacco, usando dati pubblici o tramite altri metodi, ricercano indirizzi mail o modi per contattare direttamente gli individui e ricercano [[Vulnerabilità software]] nei programmi utilizzati dalla vittima.
2. __Intrusione nella rete__: solitamente avviene quando un individuo apre una mail di phishing e scarica un PDF malevolo, o più in generale un [[Malware]], che infetta la macchina dell'impiegato e permette all'attaccante di essere già con un piede dentro la porta.
3. __Inserire una backdoor__: l'attaccante cerca di ottenere le credenziali di amministratore del dominio e le estrae dalla rete. Solitamente queste credenziali sono criptate ma basta decriptarle con degli strumenti appositi.
4. __Ottiene le credenziali__: l'attaccante ottiene la maggior parete dell'accesso utilizzando credenziali utente valide, solitamente ottenute le chiavi di accesso dell'amministratore di dominio può accedere a circa il 40% dell'intera rete.
5. __Installare varie utilities__: queste utilities vengono installati sulla rete della vittima per amministrare il sistema, come per esempio: installare backdoor, ottenere password, ottenere email, ecc.
6. __Privilege escalation, lateral movement e esfiltrazione di dati__: in questa fase solitamente fanno un backup del server e lo scaricano nei loro sistemi.
7. __Mantenere l'accesso__: se l'attaccante ha la sensazione di essere osservato può lasciare la rete finché le acque non si calmano lasciando comunque un [[Malware]] per mantenere l'accesso.

[La prevenzione per advanced persistent threat (flashstart.com)](https://flashstart.com/it/la-prevenzione-per-advanced-persistent-threat/#5-le-fasi-dellattacco-apt)