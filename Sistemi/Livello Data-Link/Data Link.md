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
questi codici sono utilizzati per correggere un certo numero di bit **O** per rilevare la presenza di errori.
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


#### CRC
**Cycling Redundancy Checks**: individua gli errori, non li corregge.
Faccio due CRC tra il frame nel mittente ed il frame del destinatario: controllo se i due CRC sono identici.
Il CRC è un **codice polinomiale** dove i coefficienti dei polinomi sono 0 o 1.

#### esercizio
$$
x^3+5x^2-6x-1.5
$$
**isoformismo**: rappresentare una equazione come un vettore (1,5,-6,-1.5)

Abbiamo ora bisogno di un polinomio speciale, chiamato **polinomio generatore**.

frame costituito da una concatenazione di due stringhe: frame stesso (espresso come polinomio) ed il **polinomio generatore**.
Quest'ultima parte viene inserito nel fondo del frame e controlla che il **frame** **inviato e quello ricevuto siano identici**.
Per questo motivo, il polinomio deve essere definito prima dell'invio del messaggio.

#### calcolo CRC
- Grado del polinomio generatore (costante) = *r*
- messaggio composto da *m* bit (payload del frame)
- Aggiungo il CRC a 0 (non lo abbiamo ancora definito)
- Moltiplico il frame per il polinomio generatore di grado *r*:  *M(x) x^r*
- Divido: divido il frame ampliato per il polinomio generatore
 




**Overhead**: spazio utilizzato dai bit di ridondanza che vengono aggiunti al frame per il controllo/correzione degli errori.
**Interleaving**: tramite speciali algoritmi, invio i bit del payload, dell'header e del trailer in modo sparso.



***

### Correzione degli errori

Per correggere un frame non valido, usiamo il **principio di massima verosimiglianza**.
In altre parole, dato un frame non valido, prendo **il code word più simile**, ovvero quello che il minore numero di bit diversi dal frame ricevuto.
Per correggere *d* bit, le code word devono avere una distanza di *2d+1*


#### DIsuguaglianza di hemming
*m*: numero di bit inviati
*r*: numero di bit di ridondanza
*n*: numero totale di bit. Numero massimo di combinazioni tra bit.

Non possiamo però utilizzarle tutte, dal momento che molte di esse non saranno code word valide; Possiamo utilizzare *2^m* combinazioni diverse.
$$
(m+r+1)*2^m
$$
numero di code word giuste o quelle che contengono solo un errore (quelle che hanno un solo bit di differenza da quelle corrette).

Per poter utilizzare i bit di ridondanza efficacemente, **Il numero di code word corrette deve essere minore di quelle totali**.
$$
(m+r+1)2^m < 2^n
$$
Semplificando:
$$
(m+r+1)<2^r
$$
La disuguaglianza di Hemming ci permette di definire il **numero minimo di bit di ridondanza** necessari in un frame per poter correggere un bit.

***

#### Organizzare i bit di ridondanza

Scelto il numero di bit da inviare, scelgo di conseguenza il numero di bit di ridondanza (tramite la disuguaglianza di Hemming).
Dando per certo che il codice sia **di autocorrezione di un bit** (capace di rilevare il bit sbagliato, per poi correggerlo).
I bit di ridondanza si inseriscono nel frame nei posti **di indice pari a potenze di due**.

#### anomalia
l'elemento di posto *0* nel frame si chiama **anomalia**, un numero intero positivo che **segnala la posizione del bit sbagliato**, ovvero quello che deve essere invertito.
L'anomalia ha come valore 0 quando non sono presenti errori nel frame.

Non viene inviato nel canale, ma solo da chi calcola il frame.

#### esercizio

**Invio del frame**
m = 8  --> 10111001
Con disuguaglianza di Hemming: r= 4 bit ridondanza

Frame composto da 12 bit (n=m+r)
Posti per i bit: 1,2,4,8.   Negli altri posti: payload
Frame totale: bb1b011b1001

Calcolo la parità: controllo se vi è parità nel frame (numero di 1 pari)
N.bit a 1: 5
Per avere parità pari, **setto un bit di ridondanza a 1**

Setto il secondo bit di ridondanza a 1 (per un algoritmo)
Setto il terzo bit di ridondanza a 1 (per algoritmo)
Setto quarto bit di ridondanza a 0 (per algoritmo)
**Frame completato ed inviabile**

**Ricezione del frame & correzione errori**
Supponiamo che Il destinatario riceva il frame con un bit sbagliato.

frame: 11110110**0**001
Per individuare l'errore, **ricalcolo i bit di ridondanza** con la stesso algoritmo.

Ricalcolando il frame, vediamo che **r1** e **r8**  sono sbagliati, mentre gli altri due sono giusti.
**La somma dei bit di ridondaza sbagliati è contenuta dentro l'anomalia**, perciò và flippato il bit di posizione 9 per correggere il frame.

#### Algoritmo per calcolo valore bit di ridonanza

**Algoritmo** per calcolare un bit di parità di posizione n:
- prendo n bit a partire dal bit di ridondanza (compreso lo stesso bit)
- non considero i successivi n bit
- Faccio somma degli 1 prelevati. In base al valore, setto a 0 o 1 il bit.
- ripetere per tutti i bit di ridonanza del frame

In base alla posizione del bit sbagliato, possiamo intuire **quale bit di ridondanza andrà a influenzare il bit**.

#### Esercizi
char1 = a = 97 = 01100001 
char2 = c = 99 = 01100011

m = 16 --> r=5 --> n=21

Frame: bb0b110b0001011b00011

R1: 0100001001 --> n.bit1 = 3 --> **R1=1**
R2: 010001100 --> n.bit1 = 3 --> **R2 = 1**
R3: 110101111 --> n.bit1 = 7 --> **R3= 1**
R4: 00010110 --> n.bit1= 3 --> **R4=1**
R5: 00011 --> n.bit1 = 2 --> **R5 = 0**

Frame ricevuto (1 errore): **11**0**1**110**1**0*1*01011**0**00011

R1: 10111001 OK
R2: 00010001 NO!
R3: 110101111 OK
R4: 0101011 NO!
R5: 00011 OK

Valore anomalia: 2+8 = 10

Frame ricevuto (2 errori): 

















