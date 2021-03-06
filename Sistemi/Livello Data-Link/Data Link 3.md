## Wireless (802.11)

Due possibilità:
- Rete mesh: rete senza access point, dove tutti parlano con tutti
- Access point: 

###### Terminali nascosti ed esposti

**Stazione esposta**: due stazioni, che si rilevano a vicenda, comunicano con la stessa stazione.

**Stazione nascosta**: due stazioni abbastanza lontane da non rilevarsi, comunicano con la stessa stazione.

##### MACA (Muliple Access Collision Avoidance)

Le stazioni possono parlare una alla volta con la stessa stazione.
E' anche possibile che più stazioni parlino con una stazione contemporaneamente; l'unica condizione è che le due stazioni mittenti **non si rilevino a vicenda**.

Il MACA si basa sull' utilizzo **due mini-frame** per:
- Informare tutte le stazioni limitrofe (rete mesh) che si sta per inviare un file (**RTS**: Request To Send)

Con questa richiesta, si sta chiedendo alle stazioni vicine di fare silenzio per un certo periodo di tempo (arbitrario).
- Stimolare la stazione ricevente per essere sicuri che sia pronta a ricevere il file (**CTS**: Clear To Send)

Nel momento in cui due stazioni inviano un RTS contemporaneamente, una delle stazioni entra in timeout, per poi riprovare ad inviare l'RTS in tempi successivi (**randomici**).

Con l'utilizzo di questi due miniframe, si è risolto il problema di eventuali collisioni di due frame di dati.
D'altro canto, permane ancora il problema di eventuali **collisioni degli RTS**.
***














