
# Data Link (another one)

## Comunicazione tra due NIC
Rete **point-to-point**: rete instaurata solo tra due host.
Bisogna fare in modo che le schede di rete riescano a comunicare fra di loro (scambiarsi messaggi, ed altre informazioni), ma rigorosamente alla **stessa velocità**. 
In caso contrario, si crea **dissincronismo** tra le due NIC e quella ricevente incomincia a perdere frame.

La NIC ricevente non riceve solo i frame, bensì li rinvia al mittente in caso fossero sbagliati (gli chiede quindi di rinviarli).
D'altro canto, una NIC deve conservare da qualche parte l'ultimo frame ricevuto, perciò usa un **buffer** per salvare l'ultimo frame ricevuto.

### Identificazione del frame
I frame, per essere distinguibili tra di loro, devono avere un **identificatore**, univoco per ogni-  frame. Questo ID si trova nell'header.


### Sliding window



#### piggyback



## Medium Access Control (MAC)

Indirizzo MAC: 6 byte divisi in
- **3 byte** identificano il produttore della scheda
- **3 byte** identificatore univoco della scheda di rete 

**Clonare una scheda di rete**: modificare l'indirizzo MAC della NIC.


## Collegamenti P2P e broadcast

Le *WAN* (ossatura di internet) per comunicare tra loro usano una rete **P2P**, ovvero un collegamento tra due router.
Le *WLAN* sono invece collegate fra di loro in una comunicazione **broadcast**.
Le *LAN*, invece, sono collegate in una rete P2P.



#### glossario
****
**Livello fisico**:
 *ripetitore*: amplifica il segnale analogico (amplificando pure eventuali errori).
 
 *hub*: permette a più schede NIC di comunicare a livello fisico. 
 Non effettua la segmentazione, ovvero ogni messaggio viene recapitato da tutte le NIC collegate all'HUB.

**Livello data link**:
*Switch*:  sostituto degli hub, effettua la segmentazione, ovvero crea una rete p2p tra lo switch (una NIC per ogni porta) ed ogni host collegato direttamente a quest'ultimo. 
Lo switch quindi **inoltra** il frame ricevuto solamente alla NIC destinataria, non a tutte.


un **brige** effettua la conversione tra un dialetto ed un altro, permettendo a schede di tipo diverso (ethernet, wireless, ecc..) di comunicare tra di loro.
Un router di casa ha **molte NIC diverse**, solo che sono viste dalla rete come un **unica NIC** (hanno lo stesso indirizzo IP)

**Livello rete**:
*Router*: indirizza i pacchetti verso il destinatario, il cui indirizzo IP si trova nell'header.
Nel caso in cui l'host destinatario non si trovi sulla stessa rete, dovrà **inviare questo pacchetto ad un router più vicino al destinatario**.
Di conseguenza, un router deve avere 2+ schede di rete, dal momento che deve.














