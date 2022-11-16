L'__Hub__ è un dispositivo di livello fisico dotato di due o più interfacce.
Essenzialmente, è un _ripetitore_ che opera a livello di singoli bit, ripete i bit ricevuti su una interfaccia a tutte le altre interfacce.
Ultimamente è da considerarsi un _dispositivo obsoleto_.

### Vantaggi dell'hub
L'Hub è un dispositivo _semplice_ ed _estremamente economico_, estende la massima distanza fra coppie di nodi.
È _trasparente_ perché non necessita di alcun cambiamento agli adattatori [[Rete LAN|LAN]] degli host e permette il _confinamento dei guasti_ perché un guasto su di un segmento [[Rete LAN|LAN]] non impedisce il traffico sugli altri segmenti.

### Svantaggi dell'hub
Gli hub _non isolano il dominio delle collisioni_, ovvero il traffico di un host può collidere con il traffico di ogni altro host ce risieda in un qualsiasi segmento della [[Rete LAN|LAN]] collegato all'hub.
In pratica, dal punto di vista del traffico, una [[Rete LAN|LAN]] collegata mediante hub è equivalente a una [[Rete LAN#Topologia a bus|topologia a bus]].