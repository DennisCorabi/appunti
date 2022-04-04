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

## Ethernet (802.03)

#### Ethernet classica

**Velocità**: 3 Mb/s - 10 Mb/s  --> cavo coax
Prima rete locale ethernet: 1976. Utilizzava un lungo cavo coax.

**DIX Standard**: Primo standard dell'ethernet a 10 mbps 
**Thick ethernet**: 
- 100 computer collegati
- lunghezza massima cavo: 500 metri

**Thin ethernet**: 
- 30 computer collegati.l
- lunghezza massima cavo: 185 metri

###### Frame ethernet
**Ethernet DIX**:  Payload (con **CRC**) + trailer + header
1.  Preambolo composto da **8 byte** (onda quadra con codifica manchester): serve per sincronizzare mittente con ricevente.
2. indirizzo MAC destinatario
3. indirizzo MAC mittente

L'ethernet classica si basa sull'uso dell' **Hub**, che invia un frame a tutte le stazioni collegate, creando di fatto una comunicazione **broadcast**.

#### Ethernet switched

**Velocità**: da 100 Mb/s a 40-50 Gb/s --> cavi UTP
Diversamente dalla ethernet classica, l'ethernet switched usa gli **switch**, che permettono di **inoltrare** un frame solamente al destinatario.

Se 2+ stazioni vogliono comunicare con la stessa NIC, lo switch decide quale dei frame deve essere inoltrato per primo alla NIC destinataria.
Le porte dello switch sono collegate tra loro all'interno del dispositivo

###### Dominio di collisione
Si usa solo per gli hub



#### Struttura del frame ethernet

- 8 byte a 01: preambolo, sincronizza mittente e destinatario
- SOF: ultimo byte del preambolo, pieno di 1, indica il l'inizio del frame vero e proprio
- MAC 6 byte destinazione
- MAC 6 byte mittente
- 2 byte di tipo frame (protocollo che sta usando) o lunghezza del frame
- dimensione variabile del payload
- (opzionale) pad se il frame è troppo piccolo
- 4 byte per FCS/CRC

Dimensione minima frame: 64 Byte (tolto il preambolo).
Se non ci fosse un ente generico che regola l'uso delle NIC, ci potrebbero più schede di rete con indirizzi MAC.

Se un frame ha un payload di grandezza minore di 1600 byte, allora viene considerato come un frame IEEE.
Se è maggiore di 1600, viene preso come un frame DIX.

###### Calcoli
Velocità ethernet classica: 10 Mb/s --> per inviare un frame di lunghezza minima: 0,000052 secondi.
**Lunghezza massima teorica  di un cavo ethernet**: 200.000 Km/s * 0,0000052 s --> 10.4 Km
**Lughezza massima reale di un cavo internet**: 5.2 Km (si conta anche l'eventuale viaggio di ritorno del frame inviato).

## Fast Ethernet (802.3u)
10 volte più veloce: usa 4 doppini al posto di 1 (ethernet classica) : 25 MHz per ogni coppia.
Usa solo cavi UTP, Coax o fibra ottica.
MDR: 100 Mbps sui 100 metri (distanza hub-computer), solo per ethernet con doppini, con fibra ottica: 2000m.

**3 Versioni**:
- 100Base-T4: UTP cat.3, 2-4 doppini
- 100Base-TX: UTP cat.5, 4 doppini
- 100Base-FX: Fibra ottica

**Auto-negotiation**: l'hub o lo switch rileva in automatico se la scheda di rete collegata è a 10Mbps (classica) o 100 Mbps (fast).
Viene deciso in automatico la velocità della connessione (10 o 100) ed il tipo (full o half duplex).


## Gigabit ethernet (802.3ab)

Non viene usato il CSMA/CD.
Se collegato ad un hub, la connessione via gigabit ethernet entra in automatico in half-duplex.
Se si vuole continuare ad usare la stessa dimensione minima (64 Byte), la gigabit deve essere più corta (25 metri massimo).
Per aumentare la lunghezza del cavo, si è dovuto aumentare la dimensione minima del frame : **512 Byte** (4096 bit).

**4 versioni**:
- 1000Base-SX: fibra ottica multimode, 550 metri
- 1000Base-LX: fibra ottica multi/single mode, 5000 metri
- 1000Base-Cx: 2 doppini STP, 25 metri
- 1000Base-T: 4 doppini UTP cat.5, 100 metri 

Vengono usati segnali a **5 livelli** di tensione.

###### Jumbo Frames

frame lunghi da 1500 bytes a 9000.
Facendo ciò, diminuiamo il frame rate (quindi l'MDR), però possiamo trasportare (?)

## 10 Gigabit ethernet

1000 volte più veloce della ethernet standard, standardizzato nel 2006.

**5 versioni**:
- 10GBase-SR: fibra ottica multi-mode, 300m
- 10GBase-LR: fibra ottica single-mode, 10Km
- 10GBase-ER: fibra ottica single-mode,  40Km
- 10GBase-CX4:  4 paia di twinax, 15 m
- 10GBase-T: 4 paia UTP cat.6, 100m

**twinax**: cavi coassiali con due cavi al suo interno, schermate da un ulteriore rivestimento.


















