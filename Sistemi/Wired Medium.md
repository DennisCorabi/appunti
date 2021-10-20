# Livello fisico
## Indice
- **Mezzi di trasmissione**
	- Cablata
	- Wireless
	- Satellitare
	- Altri
	
- **Modulazione Digitale **

## Introduzione

**Analisi di Fourier**
Nei primi anni del 19esimo secolo, il matematico francese **Jean-Baptiste Fourier** constatò che ogni segnale periodico può essere visto come  un insieme infinito di seni e coseni.

### **Bandwidth - Larghezza di banda**

La **larghezza di banda** è la quantità di informazioni (frequenze) che il mittente riesce ad inviare al destinatario. 

La larghezza di banda è una proprietà fisica del mezzo di trasmissione che dipende da lunghezza e spessore del cavo.
Più frequenze utlizzabili -> maggiore fedeltà al segnale originale -> più dati condivisi.

I segnali che vanno da una frequenza 0 alla massima frequenza disponibile sono chiamati  **Banda Base**.
Questo non è possibile nel mondo reale a causa del fatto che le frequenze sono spartite tra i vari utilizzatori.
Si chiama **Banda Passaggio** invece i segnali che non incominiciano da frequenza 0.

Nel cavo ethernet vengono utilizzate tutte le frequenze disponibili, partendo da 0 (**baseband**). Nelle trasmissioni wireless invece la frequenza di partenza non è 0, ma dalla prima frequenza disponibile (**passband**).

### **MDR: Maximum Data Rate**

l'**MDR** in un canale di comunicazione indica la quantità di informazione trasmessa in un canale di comunicazione.

Nel 1924, **Henry Nyquist** ipotizzò che neanche un canale di comunicazione perfetto (ovvero senza rumori esterni che rovinano il segnale) ha una larghezza di banda finita dovuta all’attenuazione del segnale trasportato.
Nyquist provò che un segnale in un canale perfetto può essere riscostruito utilizzando il doppio dei campionamenti: **Teorema di Nyquist**

$$
MDR = 2B \times\log(V) [b/s]
$$
Dove:
- *B*: Larghezza di banda del canale
- *V*:  insieme dei valori diversi trasferibili sul canale (**Simboli**)


Gli studi di Nyquist vengono poi rispresi e messi "sul piano reale" da **Claude Shannon** , che formulò un Teorema per trovare l'MDR un canale di comunicazione soggetto a rumori esterni: **Teorema di Shannon**

$$
MDR = B \times\log(1+S/N) [b/s]
$$
Dove:
- *B*: Larghezza di banda del canale
- *S*: Potenza del segnale inviato dalla NIC  (ovvero il segnale originale)
- *N*: Potenza complessiva del rumore a cui è soggetto il canale.
***
## Mezzi di trasmissione
Si possono utilizzare molti mezzi di trasmissione per trasmettere dei bit, i quali si differenziano dagli altri per fattori quali il prezzo, la manutenzione, l'efficienza, ecc...

### **Nastri Magnetici**
I nastri magnetici sono uno dei più comuni mezzi utilizzati per trasmettere dati da un computer ad un altro grazie al loro rapporto spesa/bandwidth.

lo standard industriale è l'**ultrium tape**, che può contenere fino a 800 gb ed è grande pochi centimetri.

### **Cavi Twister Pair**
Uno dei più comuni mezzi di trasmissione sono i **cavi twister pair**.
Questo cavo è composto da due fili di rame, di spessore 1mm, intrecciati tra di loro, formando così una struttura ad elica.
Il segnale viene trasportato sotto forma di **differenza tra i voltaggi** dei due fili.

Nei cavi possono essere presenti più coppie di fili intrecciati tra di loro in parallelo.


**Perchè si usano i cavi intrecciati?**
Si usano cavi intrecciati così da renderli immuni alle influenze di altri campi elettromagnetici e distrurbi.
Più stretti sono i cavi --> Più sono immuni ai disturbi --> Maggiore MDR (e maggiore costo).

**Utilizzo**
I cavi twisted pair vengono utilizzati nelle linee telefoniche e per il collegamento ad internet.

**Manutenzione**
Ii segnali in questi cavi possono percorrere molti chilometri senza amplificatori di segnale.
Su più lunghe distanze, invece, il segnale si attenua e vengono utilizzati i ripetori.

**Tipologie**
- **Per struttura:**
	- **UTP** (Unshielded Twisted Pair): cavo composto dai fili e dal rivestimento isolante.
	- **STP** (Shielded Twisted Pair): i cavi sono coperti da un ulteriore rivestimento di materiale isolante.

- **Per collegamento**:
	-  **Full Duplex**: *collegamento bidirezionale*: se sto inviando, riesco anche a ricevere il segnale.
	- **Half Duplex**: *collegamento monodirezionale*: se sto invando, non riesco a ricevere il segnale.
	- **Simplex**: collegamento monodirezionale dove posso solo ricevere il segnale, ma non inviarlo.

### **Cavi Coassiali** 
Il **Cavo Coassiale** viene è un mezzo di trasmissione dati ad oggi non molto utilizzato.

Ha una protezione dai rumori ed una larghezza di banda migliore rispetto ai cavi twisted pair.
Avendo una larghezza di banda maggiore, il segnale riesce a percorrere più spazio e ad una maggiore velocità.

I cavi coassiali più recenti hanno una larghezza di banda che raggiunge l'ordine dei *GHz*.

**Struttura**
Un cavo coassiale è composto da un'anima di rame, rivestito da isolate, ricoperta di un materiale conduttore, rivestita da un materiale plastico.

**Tipologie**
- **Per utilizo**
	- **50 Ohm**: utilizzato per la trasmissione digitale
	- **75 Ohm**: utilizzato per la trasmissione analogica e televisiva.

Questi cavi sono stati pesantemente rimpiazzati dalle fibre ottiche.

### **Fibra Ottica**

La **fibra ottica** è un mezzo di trasmissione, ampiamente utilizzato ai giorni nostri, che utilizza la luce per trasportare i bit da trasmittore al ricevente.
La presenza di luce viene codificata con un *1*, mentre l'assenza di luce con uno *0*.

Una connessione in fibra ottica è composta da *tre* elementi fondamentali:
- **La fonte di luce** (mittente)
- **Il mezzo di trasmissione** (cavo in fibra) 
- **RIcevente** (destinatario)


**Funzionamento**
1) Un impulso elettrico viene dapprima convertito in un impulso di luce.
2) Da una fonte di luce viene poi generato il segnale in questione e viene "instradato" nei cavi in **fibra ottica** per raggiungere la destinazione.
3) Il fotone, giunto a destinazione viene riconvertito in segnale elettrico.

La conversione da segnale elettrico a impulso luminoso e vicevesa viene effettuata dal **convertitore opto-elettronico**.

Esssendo presenti un solo generatore di luce ed un solo ricevente, si può dedurre come la comunicazione, tramite un solo cavo di fibra ottica, sia per forza di tipo **simplex**.

Per ottenere una comunicazione **Duplex**, bisogna disporre di due  cavi in fibra ottica ed una fonte di luce e ricevitore da tutte e due le parti.

**La luce in viaggio**
La luce viaggia in un cavo sottilissimo e "**rimbalza**" (o meglio, riflette) continuamente sulle pareti del cavo.
L'angolo con cui il fotone si riflette dipende dall'**indice di rifrazione** del vetro in questione.

**Composizione**
I cavi in fibra ottica sono molto simili ai cavi coassiali.
1. Al centro vi è un **core** di vetro dove la luce rimbalza.
2.  Il core è poi rivestito dal **cladding**, composto da un materiale a basso indice di rifrazione, che ha il compito di trattenere tutta la luce.
3.  Infine vi è il **rivestimento** in materiale isolante.

In un cavo di fibra ottica possono esserci più fili (almeno due e sempre multipli di 2).

**Tipologie**
In base a quali tipologie di raggi sono supportati, le fibre ottiche si dividono in:
- **Single-Mode**: capace di portare un **solo**  tipo preciso di frequenza di luce.
Ha un costo maggiore e viene utilizzata sopratutto nel trasporto a lunga distanza (fino a 100 gb/s per 100 Km senza bisogno di un amplificatore).
- **Multi-Mode**: capace di portare **diverse** tipologie di frequenze di luce.
prezzo minore ma necessita di maggiore manutenzione.

**Generazione del fascio di luce**
Per instradare i segnali in fibra ottica si utilizzano diverse fonti di luce, tra le quali le più importanti sono:
- **LED**: basso MDR, multi-mode, a basso costo e bassa sensibilità a temperatura.
- **Laser a semiconduttore**: Alto MDR, multi/single-mode, costoso ed alta sensibilità alla temperatura.

Sensibilità al rumore nulla in tutti e due i casi.

**Velocità di trasmissione**
Per loro natura, gli impulsi di luce viaggiano nel cavo di fibra ottica alla **velocità della luce**.
La massima larghezza di banda **teorica** delle fibre ottiche è di *50.000 Gb/s*
La larghezza di banda attualmente più grande per una fibra ottica è di *100 Gb/s*.

**Fibre ottiche VS rame**
- **Pro della fibra ottica**
	- **Efficienza**: La fibra ha una maggiore larghezza di banda rispetto al rame.
	- **Manutenzione**: i ripetitori idi segnale in fibra ottica possono essere distanti fino a 50 Km tra loro, quelli per il rame massimo 5 (con conseguente risparmio di denaro per installazione e manutenzione) .
	- **Peso**:La fibra è più leggera del rame (100 Kg/Km VS 8000 Kg/km ).
	- **Costo**: La fibra ottica è più costosa del rame, ma per il suo rapporto peso/chilometro (VEDI SOPRA), diventa economicamente vantaggiosa.

- **Contro della fibra ottica**
	- **Comunicazione unidirezionale**: per sua natura, la fibra ottica permette una comunicaizione **simplex**.
	- **Fragilità**: il cavo in fibra ottica si spezza facilmente se piegato.

***














