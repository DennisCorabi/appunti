# Data Link

## Introduzione

Il livello **data link** è il livello superiore al livello fisico e svolge importanti funzioni:
- Creare una intefaccia per la schede di rete (definire le funzioni a livello kernel utilizzabili dalla NIC).
- Possibilità di cambiare il **MAC address** della schede di rete.
- Gestione degli errori ricevuti
- Regolazione del flusso dei dati (far si che le due schede di rete abbiano la stessa velocità).

I livello data link può offrire vari servizi:
- **Unacknowledged connectionless**:  i pacchetti in cui è diviso il frame percorrono strade diverse per giungere dal destinatario; non per forza, quindi, i pacchetti del frame arrivato nell'**ordine in cui sono stati spediti**. **NON** si ha la conferma di ricevuta del pacchetto.
- **Acknowledged connectionless**: simile al precedente, solo che si ha la conferma che i singoli pacchetti sono arrivati al destinatario


### Framing dei bit

I frame sono di **dimensione variabile**; per questo motivo, sono presenti diverse tecniche per indicare che il frame è finito:
- **Byte Count**:  nell'header del frame, viene indicata la grandezza del frame; se di creano però degli errori nel byte count, allora è un problema per tutto il frame.
- **Coding violation**: alcuni bit del canale sono utilizzati per indicare la grandezza del frame
- **Flag byte**: Quando la scheda di rete si trova un **flag byte**, identificato grazie ad una sequenza di escape (**ESC**), lo interpreta come la fine del frame. 
Un flag byte identifica l'**inizio** e la **fine** del frame; quando sono presenti due flag, senza nulla nel mezzo, allora la NIC sa che **sta iniziando un nuovo frame**.

il **preambolo** sono tutti quei byte, inseriti all'inizio del frame, servono sincronizzare mittente e ricevente, segnalando che sta incominicando un nuovo fram

### Incapsulamento del frame
Il frame è composto da  **tre elementi**:
- **Payload**: contenuto del pacchetto dati
- **Header**
- **Trailer**: ultimi byte del frame, servono per compiere un controllo sugli errori.


Quando due schede di rete comunicano tra di loro, devono determinare una velocità per la comunicazione identica per tutte e due le schede; solitamente è la **velocità più bassa***.
Il pacchetto di bit si chiama **frame** nel livello data link.

La scheda di rete ricevente deve prima sapere quando il frame inizia, e quando finisce.
Alla fine del frame, ci sono **4 Byte***, i quali sono chiamati **FCRC**.
Non importa quanto sia grande il frame, l'FCRC è di grandezza 4 Byte (anche se con frame molto grandi potrebbero non bastare).

**MAC**: indirizzo hardware di una scheda di rete a livello data link.
L'indirizzo MAC è composto da **48 bit**, ovvero **6 Byte**.
- I primi 3 byte identificano il costruttore della scheda
- Gli altri 3 identificano la scheda, discriminandola dalle altre

A differenza degli indirizzi IP, il separatore tra i Byte dell'indirizzo è il *:*

**Driver della NIC**: driver che permette al sistema operativo di comunicare con la scheda di rete.

## Tipologie di comunicazione tra NIC

- **Point-to-Point**: canale utilizzato **SOLO** per far comunicare due NIC
- **Multicast**: lo stesso canale viene utilizzato da più schede diverse

Il **multicast** è una tecnica che presenta molti problemi, primo fra tutti la **collisione*** che si crea quando più schede di rete vogliono comunicare sul canale simultaneamente.
Per ovviare a questo problema, bisogna utilizzare uno **schedulatore**, per regolamentare il traffico nel canale.

***
## Controllo degli errori

### Rilevazione degli errori

#### Bit di parità
**bit di ridondanza**: Bit aggiunti al frame che vengono usati per rilevare eventuali errori nel frame inviato (verifica l'integrità del frame) ed eventualmente, correggerli.

Il **tasso di errore** è il rapporto tra il numero di bit inviati sbagliati e quelli corretti.
Per ricavare il numero di bit corretti, invece, facciamo: $$1-tasso dierrore$$
Per ricavare la probabilità che tutti i bit del frame siano sbagliati, facciamo:

$$ tassodierrore*numerobitframe $$

*Esempio*:
- Ho 7 bit., aggiungo un bit, chiamato **di parità**. Si chiama bit di parità perchè aggiungiamo un 1 o uno 0 in base a **se il numero di 1 è pari**.

Un errore si può anche manifestare nel bit di parità.


#### Codici di Hamming
Il frame conterrà *m* bit di informazione, al quale aggiungeremo *r* bit di ridondanza.
Perciò, la grandezza totale del frame è *m+r* bit.

**Definizioni:**

 I **codici di hamming** sono codici utilizzati per la correzione di errori dentro un frame.
 
Una **code word** è un frame valido che possiamo ricevere, ovvero che possiede una codifica accettabile (che non contiene errori).
Il **code rate** è un numero di code word che riesco ad inviare al secondo.

**L'efficienza del frame** è una proprietà che ci permette di capire quanti bit possiamo usare per inviare dati. La formula è:
$$
efficienza=m/n
$$

L'efficienza sarà sempre un valore compreso tra *0 * e *1*.

La **distanza di Hamming** è la differenza tra i valori diversi tra due stringhe.
**Legal codewords**: sono stringhe di bit che non contengono alcun errore (i bit sono tutti corretti). 


Per far sì che un errore non venga rilevato nel frame, dobbiamo cambiare **tanti bit quanti sono i bit di parità**.

### Correzione degli errori

Per correggere un frame non valido, usiamo il **principio di massima verosimiglianza**.
In altre parole, dato un frame non valido, prendo **il code word più simile**, ovvero quello che il minore numero di bit diversi dal frame ricevuto.

P

















