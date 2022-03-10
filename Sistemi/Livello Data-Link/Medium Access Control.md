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

###### Aloha

**Allocazione dinamica del canale**:
- No carriers sense
- tempo continuo (svantaggio)

Si appoggiava un satelletite GEO (molta latenza)
Nella sua versione originale, Anche se rilevava una collisione, l'Aloha continuava ad inviare il segnale (inutilmente).

**Throughput**:  uso efficiente del canale.
**Aloha slotted**: i frame ora possono essere inviati solo in momenti precisi. Ha un maggiore throughput rispetto all'Aloha puro.


###### Carrier Sense Multiple Acess Protocols (CSMA)
Effettua il carrier control (controlla in anticipo che il canale non sia in uso da qualcuno).










 
