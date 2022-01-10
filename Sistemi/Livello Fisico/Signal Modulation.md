# Signal Modulation

## Introduzione

I canali wireless e cablati trasportano informazinoni sotto forma di segnali analogici (differenza di voltaggi , intensità di luce, ecc).
Per trasmettere segnali digitali dobbiamo **Modulare** i segnali analogici cosicchè rappresentino i **Bit**.

**Modulazione**: 	processo di conversione dai **bit** ai segnali che li rappresentano.

## Modulazione

Prima di convertitre i bit in segnali, dobbiamo prima distinguere due casistiche:
- Modulazione in **banda base**
- Modulazione in **banda passante**

### Modulazione in banda base

La forma più comune di modulazione di un segnale in banda base (ovvero dei cavi) è quella di utilizzare un voltaggio positivo come un **1** ed un voltaggio negativo come uno **0**.
Questo schema è chiamato **Non-Return-to-Zero** (*NRZ*).

Una volta inviato il segnale, il ricevitore ottiene le informazioni **campionando** il segnale ad intervalli regolari.
Essendo il canale soggetto a rumori esterni, il ricevitore decodifica il segnale in bit considerando il **simbolo più vicino** al segnale ricevuto.

#### Efficienza di Banda

TODO

#### Clock recovery
Per effettuare una corretta trasmissione e decodifica dei dati, trasmittente e ricevitore devono essere **Sincronizzati**.
Per questo motivo, in un canale di comunicazione esiste il **clock**, un orologio interno che scandisce il "**ritmo**", ovvero quando il simbolo da inviare è terminato e quando ne sta incominciando un'altro.

Con la codifica **NRZ**, però, lunghe sequenze di *0* o *1* possono portare al fenomeno del **Dissincronismo**, ovvero quando il ricevitore non riesce più a decodificare efficacemente il segnale.
Per questo motivo, ad oggi sono utilizzate due codifiche risolvono, in tutto o in parte, questo problema: le codifiche **Manchester** e **NRZI**.

#### Codifica Manchester

La codifica **Manchester** fornisce un modo semplice per codificare sequenze binarie arbitrarie senza mai aver lunghi periodi di tempo privi di transizioni di clock (**Clock recovery**), il che permette di prevenire la perdita della sincronizzazione del clock.

Nella codifica manchester i due sono presenti due segnali: 
- Il segnale dei dati
- Il segnale del **clock**.

Per risparmiare una canale di comunicazione, i due segnali sono sottoposti ad una **XOR** , che permette di utilizzare un **solo canale di comunicazione** a discapito però della larghezza di banda (ne serve il **doppio**).

La codifica manchester è ampiamente utilizzata nei cavi ethernet.

#### Codifica NRZI

La codifica **NRZI** (**Non-Return-to-Zero Inverted**) definisce un *1* quando vi è un **cambiamento** del segnale (alto-basso, basso-alto non fa differenza) ed uno *0* quando il segnale **non varia**.

La codifica NRZI viene ampiamente utilizzata nello standard **USB** e nei **CD**.

**4B/5B**
A differenza della codifica Manchester, però, la codifica NRZI non risolve del tutto il problema del **dissincronismo**; Viene risolto solo nel caso degli *1* (dove si ha continua commutazione del segnale), mentre nel caso degli *0* il segnale continua ad essere fermo.

Per ovviare a questo problema viene utilizzata la tecnica **4B/5B**, che "spezzetta" il segnale in coppie di **4 bit** e li codifica in un segnale a **5 bit** (seguendo una tabella di conversione) , che serve a non avere più di 3 *0* vicini fra di loro.

Infine, il ricevitore, conscio dell'uso di questa codifica, **decodifica** il segnale (sempre seguendo la tabella di conversione) e ri-ottiene così il segnale originale. 

**Scambler**
Come alternativa alla codifica **4B/5B** si può far uso dello **scrambler**, un software che codifica il segnale da inviare in modo casuale, per poi essere decodificato una volta giunto a destinazione.

Lo scramber, per codificare il segnale, effettua una **XOR** tra il segnale da inviare ed una sequenza random di *0* ed *1*.
Per ricavare il segnale originale, lo scrambler effettua una **XOR** utilizzando la medesima sequenza di bit.









