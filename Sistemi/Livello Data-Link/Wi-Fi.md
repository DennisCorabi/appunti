# Wireless (802.11)


##### struttura
Serve un access point per collegarsi ad una rete wireless.

Gli access point sono  collegati fra loro con cavi in rame, per garantire una maggiore resistenza ai rumori ed una banda maggiore.

###### versioni

- 802.11 (legacy)
- 802.11a: 5 GHz
- 802.11b
- 802.11g
- 802.11n

###### Livello fisico
Le NIC wireless usano onde a basso raggio. 
Lo standard 802.11 impone come limite di potenza delle NIC wireless ad 1 Watt.


usa 52 sotto-portanti (52 canali utilizzabili), di cui solo 48 trasportano dati (le altre 4 vengono usate per sincronizzazione).
Simboli a **64 bit** (1/2, 1/3, o 1/4 di questi bit sono usati per ridondanza, correzione errori),

la 802.11n: MDR di almeno 100Mbps. All'inizio vi era un solo canale da 20MHz, poi è stato duplicato aggiungendo un canale identico.

###### Livello Data link
802.11 usa **CSMA/CA** (CSMA with Collision Avoidance). Uso dell' **exponential backoff** e del **MACA**

**Beacon**: segnale che viene inviato dalla NIC ogni 100ms per far notare la sua presenza alle NIC nella rete wireless.




