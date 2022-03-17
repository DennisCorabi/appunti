# Medium Access Control (MAC)

### Allocazione del canale
**Collisione**:
Due frame nello instante condividono la stessa porzione di canale.

###### Allocare il canale in maniera statica: 
uso del TDM, FDM o CDMA.
Non è fattibile perchè servirebbe un arbitro che gestisce il tutto.

###### Allocare il canale in maniera dinamica: 
**traffico indipendente**: le stazioni comunicano quando vogliono ed in maniera del tutto indipendente.
**Singolo canale**: abbiamo un singolo canale a disposizione.
**Tempo continuo o diviso (slotted)**: se possiamo inviare un frame quando vogliamo, o abbiamo dei momenti in cui possiamo inviare un frame.
**Carrier/No Carrier sense**: segnale che usiamo per trasferire segnali al ricevente (segnale portante).  **Carrier sense** vuol dire controllare che la portante sia libera (che nessuno sta usando il canale).


### MAC

##### Aloha

**Allocazione dinamica del canale**:
- No carriers sense
- tempo continuo (svantaggio)

Si appoggiava un satelletite GEO (molta latenza)
Nella sua versione originale, Anche se rilevava una collisione, l'Aloha continuava ad inviare il segnale (inutilmente).

**Throughput**:  uso efficiente del canale.
**Aloha slotted**: i frame ora possono essere inviati solo in momenti precisi. Ha un maggiore throughput rispetto all'Aloha puro.


##### Carrier Sense Multiple Access Protocols (CSMA)
Effettua il carrier control (controlla in anticipo che il canale non sia in uso da qualcuno). Non si usa con reti wireless.

 **persistente?**
###### Binary Exponential Backoff

Pacchetti che devono essere inviati devono aspettare un tempo randomico prima di essere inviati. Questo per evitare che si creino collisioni.
Bisogna trovare un sistema che si **adatti** al traffico corrente del canale.

L'algoritmo che crea un timeout variabile dinamico si chiama **backoff**.
Dalla decima collisione in poi, il range del numero random da genererare rimane costante (1024 slot massimi).
Dalla secidesima in poi, la NIC viene del tutto disattivata.

L'unità di misura è lo slot (unità di tempo in cui si possono inviare i frame).
Il numero generato definisce **il numero di slot che deve aspettare il frame per essere inviato** (sempre se non ci sono ancora collisioni).

##### CSMA with Collision Detection (CSMA/CD)

Un frame è inviabile senza collisioni nel momento in cui il suo primo bit arriva  a tutte le altre schede di rete del canale.
**tau**: periodo di tempo che serve al frame di raggiungere la NIC più lontana.
Per evitare collisoni, dobbiamo occupare il canale per almeno **due tau** (andata e ritorno del frame).

**Dimansione del frame minima**: un canale ha una grandezza minima. nel caso in cui un frame non rispetti la grandezza minima, allora la NIC aggiunge degli 0 all'inizio del frame.

##### CSMA with Collision Avoidance (CSMA/CA)

Protocollo derivato dal CSMA la cui particolarità è che **non ci sono collisioni**,
Le stazioni si trovano in un **contention slot**.

Le stazioni, in base al loro ordine del contention slot, **prenotano** il canale se devono inviare il frame.
Dopodichè, incomincia l'invio dei frame dalle stazioni che hanno prenotato il canale (nell'ordine di prenotazione).

D'altro canto, questo protoccolo non è efficiente perchè le stazioni devono aspettare che le NIC di posto precedente abbiano finito di inviare il loro frame.
Per quanto riguarda l'inserimento di altre stazioni del canale, dovremmo riavviare tutto il canale per poter modificare il contention slot.

##### Token passing
Chi ha il **gettone** può inviare il frame. Il gettone è a sua volta un frame.
Il token viene passato in una rete point-to-point e half-duplex, chiamata  **token ring**.

Una stazione **non può inviare** ad una stazione in particolare il frame, bensì deve **percorrere tutto l'anello**.

##### Contention contest

Protocollo tipico della rete ethernet.











 
