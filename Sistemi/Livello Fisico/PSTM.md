# PSTN

## PSTN (Public Switched Telephone Network)

Tecnologia utilizzata per comunicazioni con telefoni fissi
- **Rete completamente interconnessa**
- **Rete centralizzata monolivello**
- **Rete centralizzata a doppio livello**


### Local-loop e End-office

collegamento finale che collega la centralina locale, chiamata anche **end-office**, al nostro telefono.

### Tool-offices

**toll**:Tariffa delle singole telefonate in base al tempo di chiamata e alla distanza dai due interlocutori.

I **toll-offices** sono delle cabine di più alto livello che comunicano direttamente con l'End-office e gli **switching-offices**.
il tool-office gestisce il prefisso locale (Es. 0341 per Lecco)

I tool-offices sono delle cabile di un livello più alto rispetto all'End-office.


### POP (Point OF Presence)

Punto di comunicazione tra due modem. Il provider da a disposizione una serie di modem ai quali si può collegare il nostro modem.
Permette, quindi, di connettere la nostra LAN ad internet grazie ad una comunicazione modem-modem (**dial-up**).


### Local number Portability

Strumento che permette di cambiare provider, ma senza cambiare il numero di telefono.
Il telefono viene quindi trasportato da una SIM all'altra.

### Modem telefonico

Il Modem (**MO**dulator and **DEM**odulator) è uno strumento che trasforma da analogico a digitale o viceversa un segnale.
- Nel **modulatore**, entra digitale ed esce analogico.
- Nel **demodulatore**, entra analogico e esce digitale.


#### Canale telefonico

Un canale telefonico utilzza solitamente 3KHz di frequenza, il minimo per avere una comunicazione ottimale.
Anche se il symbol rate con 3 Khz massimo è di 6000 Baud (simboli/secondo), è stato tagliato a **2400** per non avere problemi.
In verità, una comunicazione telefonica occupa **4KHz**: 3 vengono utilzzati per la comunicazione, il resto, a destra  e a sinistra della banda utilizzata, viene utilizzato per evitare interferenze fra i vari utilizzatori della banda.


La frequenza massima di una linea telefonica è di **56 KHz**.
Si poteva andare olte (ca. *70KHz*), ma il resto viene utilizzato per controllo di errori.

