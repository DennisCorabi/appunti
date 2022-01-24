
# Socket
Permette a due processi su macchine diverse di comunicare tramite un **protocollo** per comunicare (**Intra process communication**)

Socket: **server** e **client**.
Server: processo che rimane in ascolto in una porta in attesa di una richiesta da parte di un client.
Per poter gestire tanti client contemporaneamente, uso il multithreading.

Utilizza le socket UTP per lo stream audio e video.
Per aprire una porta inferiore a **1024** devi essere utente root.



#### Comandi
-  **ss -u**: visualizzare le socket UTP attive
-  **ss -t**: visualizzare socket TPL attive
-  **ss -tl**: visualizzare le socket TLP in ascolto.
-  **ss-tln**: visualizza in aggiunta il numero della porta.

**Send-q**: coda dei pacchetti da inviare
**Recv-q**: coda dei pacchetti ricevuti

#### Chiamate
- **Bloccanti**: bind, listen