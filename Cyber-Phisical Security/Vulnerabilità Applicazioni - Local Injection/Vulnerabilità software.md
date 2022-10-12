Vi sono molteplici vulnerabilità software che possono essere sfruttate dagli _attacker_ per compromettere il sistema, soprattutto le vulnerabilità possono riscontrarsi ovunque intervenga il software:
- Protocolli.
- Sistemi operativi.
- Processi dei server.
- Applicazioni.

## Ciclo di vita di una vulnerabilità software
![[Screenshot_20221008_145427.png]]
Il periodo di tempo, che intercorre tra la data dal rilascio dell'exploit nel mondo e quando la vulnerabilità viene riconosciuta pubblicamente, si chiama __zero-day attack__, questo termine fu coniato nei primi anni '90 dai cracker di software e relativi utenti.
Quando viene pubblicamente riconosciuto fino a quando viene messa una patch al problema, quest'ultimo persiste ma con una forza ridotta rispetto al periodo __zero-day__.

## Classi di vulnerabilità
Queste sono alcune classi di errori che affliggono molto del software esistente:
- [[Mediazione incompleta]].
- [[TOCTTOU|Tempo di controllo/tempo di utilizzo]].
- [[Code injection]]: 
	- Buffer overflow + shellcode injection.
	- SQL injection.
	- Cross-site Scripting (XSS).
	- ...