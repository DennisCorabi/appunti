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

## **MDR:** Maximum Data Rate
l'**MDR** in un canale di comunicazione indica la qta di informazione trasmessa in un canale di comunicazione.
***
## Nastri Magnetici

lo standard industriale è l'**ultrium tape**, che può contenere fino a 800 gb.
***
## Twisted Pair

Nei cavi sono presenti dei cavi intrecciati tra di loro a coppie di due.
**UTP**: Unshielded twisted pair
**STP**: Shielded twisted pair (I cavi sono coperti da un ultreriore rivestimento di rame).

Diverse tipologie di collegamento:
- **Full Duplex**: *collegamento bidirezionale*: se sto inviando, riesco anche a ricevere il segnale.
- **Half Duplex**: *collegamento monodirezionale*: se sto invando, non riesco a ricevere il segnale.
- **Simplex**: collegamento monodirezionale dove posso solo ricevere il segnale, ma non inviarlo.

### Perchè si usano i cavi intrecciati?

Si usano cavi intrecciati così da renderli immuni alle influenze di altri campi elettromagnetici e distrurbi.
Più stretti sono i cavi --> Più sono immuni ai disturbi --> Maggiore MDR (e maggiore costo).
***
## Cavi Coassiali

Composto da un'anima di rame, rivestito da isolate, ricoperta di un materiale conduttore, rivestita da un materiale plastico.

Due tipologie: 
- Cavi 50 Ohm
- Cavi 75 Ohm

Questi cavi sono stati pesantemente rimpiazzati dalle fibre ottiche.

***
## Fibra Ottica

Utilizza la luce per trasportare i bit da trasmittore al ricevente.
Ad oggi le fibre ottiche possono trasportare segnali per decine di chilometri.

Abbiamo bisogno di due interfacce, che trasfromino un impulso di luce in elettricità e viceversa (**Convertitore Opto-Elettronico**).

La massima larghezza di banda teorica delle fibre ottiche è di 50.000 Gb/s.
La larghezza di banda attualmente più grande per una fibra ottica è di 100 Gb/s.

### Composizione
- Jack plastico (rivestimento in plastica)
- cladding (rivestimento in vetro)
- core (dove viaggia il fotone di luce)

**indice di rifrazone**: permette alla luce di non "uscire" dal core e di non essere assorbita dal cladding.

In un cavo di fibra ottica possono esserci più fili (almeno due e sempre multipli di 2).
Vengono utilizzati multipli di due per creare una comunicazione duplex, dal fatto che i cavi di fibra ottica sono simplex.

### Tipologie di fibre ottiche
vi sono due tipologie di fibre ottiche

- **single-mode**: capace di portare un tipo preciso di frequenza di luce.
ha un costo maggiore e viene utilizzata sopratutto nel trasporto a lunga distanza (trasmette fino a 100 gb/s senza bisogno di un amplificatore).

- **multi-mode**: capace di portare diverse tipologie di frequenze di luce.
prezzo minore ma necessita di maggiore manutenzione.

**lunghezza d'onda * frequenza = c (velocità della luce)**

### Come instradare i segnali in fibra ottica

Si possono usare diversi strumenti per inviare segnali in fibra ottica:

- **LED**: Basso MDR, multi-mode, a basso costo e bassa sensibilità a temperatura.

- **Laser a semiconduttore**: Alto MDR, multi/single-mode, costoso ed alta sensibilità alla temperatura.

Sensibilità al rumore nulla in tutti e due i casi.

***

## Fibre ottiche VS rame
- **Ripetitori di segnali**: i ripetitori in fibra ottica possono essere distanti fino a 50 Km tra loro; Quelli per il rame massimo 5.

- La fibra è **più leggera** del rame (100 Kg/Km VS 8000 Kg/km ).

- fibra ottica più costosa del rame, ma per il suo rapporto peso/chilometro (VEDI SOPRA) diventa economicamente vantaggiosa.












