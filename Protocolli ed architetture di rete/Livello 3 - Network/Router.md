Un __router__ è un dispositivo il cui compito è quello di _instradare_ i pacchetti nella rete da qualsiasi altro host, sulla base dell'[[indirizzo IP]] destinazione incluso nel pacchetto stesso.

## Inoltro pacchetti hp-by-hop
I router si passano i pacchetti hop-by-hop: nessuno decide il percorso complessivo, ma solo il router successivo.
Infatti un host che invia un pacchetto all'_esterno della propria rete locale_ deve decidere tramite router di inviarlo: quest'ultimo viene detto _source router_.
Ogni router deve de