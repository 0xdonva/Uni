Il __firewall__ è un dispositivo di sicurezza che si interpone tra due reti diverse per controllare e limitare il traffico.
Il firewall deve essere l'unico punto di contatto tra la rete esterna e la rete interna, solo il traffico autorizzato o non vietato deve riuscire ad attraversare il firewall.
Il firewall deve essere, a sua volta, un sistema sicuro e tenuto sempre sotto controllo.

## Politiche di sicurezza
### Negazione implicita
Solo il traffico esplicitamente autorizzato può attraversare il firewall.
Tutto il traffico non esplicitamente autorizzato viene bloccato:
- È il metodo più sicuro di firewalling.
- Dal punto di vista degli utenti è il più restrittivo.
- È più difficile da gestire.

### Accesso implicito
Solo il traffico esplicitamente vietato viene bloccato dal firewall.
Tutto il traffico non vietato esplicitamente può attraversare il firewall:
- Garantisce la massima usabilità della rete.
- È più facile da gestire.
- Espone la rete a rischi di sicurezza.

## Tipologie di firewall
Si possono identificare due tipologie principali di firewall sulla base delle funzionalità offerte:
- [[Firewall Packet Filter]]
- [[Firewall Application Gateway]]