# Threads

## Threads
I **thread** sono dei **sottoprogrammi** che compiono una certa funzione, rigorosamente in **parallelo** ad altri thread.
I thread possono condividere dei **dati** (variabili, file, ecc...), chiamate **risorse critiche**.

#### risorse condivise
I thread di uno stesso programma condividono il **code segment** ed il **data segment**; in particolare, sono questi gli elementi condivisi fra tutti i thread:
- Address space
- File aperti
- Variabili globali 
- inserire altre cose

#### risorse non condivise (proprie del thread)
Lo **stack segment**, invece, è proprio per ogni thread.
Oltre allo stack, i thread hanno degli elementi non condivisi con gli altri:
- Program counter
- Registri
- Lo stato 

I thread, a differenza di processi normali, non usa un PID, bensì usa un **TID** (**T**hread process **ID**entificator).

I thread hanno un limite di grandezza dello stack; Se esso viene superato, si avrà uno **Stack Overflow**.

#### API
le **API** (Application Programming Interface) sono l'insieme di funzioni con le quali possiamo interfacciarci con le librerie.



## Funzione Pthread

La funzione **Pthread** è una funzione appartenente alla libreria **POSIX** e serve per creare dei thread del processo che la chiama.

Per utilizzare i thread, bisogna aggiungere il parametro *- pthread* durante la compilazione del sorgente dal terminale.


### Creare Thread

I thread si possono creare all'interno di un programma in C chiamando la funzione *pthread_create*, che lo rende anche eseguibile.

Gli argomenti della funzione sono:
- Posizione al parametro che utilizza la funzione passata come 3° parametro
- puntatore ad una funzione (puntatore alla prima istruzione di una funzione)

I thread possono a loro volta creare altri thread dal momento che **NON** vi è una gerarchia fra i thread.

### Stoppare un thread

I thread si possono stoppare all'interno di un programma invocando la funzione *phtread_join*, la funzione **wait** dei thread.


### Sospendere un thread
un thread in esecuzione si può **auto-sospendere** in un programma invocando la funzione *pthread_yield*, la quale rilascia la CPU per permettergli di eseguire un altro thread.

### Terminare un Thread

I thread possono essere terminati utilizzando la funzione *pthread_exit*, dove mando una richiesta al thread di **suicidarsi**.


## Problemi tra i thread

**Zone critiche**: regioni in comune con i thread (es. variabili globali)
**corse critiche**: funzioni che utilizzano risorse critiche (condivise tra i vari thread)
**risorsa critica**: Variabile globale utilizzata dai thread scrivibile e leggibile.
**stallo**: situazione in cui due o più thread aspettano **contemporaneamente** che un'altro di questi thread acceda alla risorsa critica.
Di conseguenza, nessuno dei thread accederà alla risorsa critica.


Per evitare problemi di lettura/scrittura di una risorsa critica tra più thread, si instaura un "semaforo", che indica ad un thread se si può accedere alla variabile.
- Se è "**verde**": si può leggere la variabile (dal verde passa al rosso)
- Se è ""**rosso**"": aspetto fino a quando la risorsa ritorna disponibile.

I semafori possono essere implementati in una programma  in C utilizzando le variabili **Mutex**.

### Mutex

le variabili **Mutex** (**Mut**ual **ex**clusion) vietano a due o più thread di accedere ad una variabile contemporaneamente.
In C, le variabii mutex sono chiamate *pthread_mutex_t*.
Per **ogni variabile critica** ci deve essere una variabile mutex associata.

Se vi è una variabile mutex, la probabilità **corse critiche** si annulla (non ci possono essere errori).


## Chiamate di sistema bloccanti

Sono presenti delle chiamate di sistema, dette **bloccanti**, che, una volta chiamate, **bloccano il processo** fino a quando non ottengono il dato desiderato.
Un esempio di chiamata di sistema bloccante è la **scanf**; una volta chiamata, infatti, blocca il programma fino a quando non ottiene qualcosa da tastiera.

In aggiunta, sono presenti delle versioni di queste chiamate di sistema che **non sono bloccanti**.

Con le chiamate di sistema non bloccanti e gli **interrupt** (segnali elettrici che vengono inviati alle periferiche), si riesce a creare una sorta di **parallelismo**; d'altro canto, questa tecnica è sconsigliata, a favore invece dell'utilizzo dei **thread**.

vedere pag. 104 figura 2.11


## Risorse critiche

### Corsa critica
Una **corsa critica** avviene quando due o più thread vogliono accedere ad una variabile globale presente nel data segment.

Una corsa critica può avvenire anche tra due **processi** che vogliono accedere ad un dato (variabile, file, ecc..) condiviso.

### Regione critica
Per evitare di creare delle corse critiche, dobbiamo creare un sistema di **mutual exclusion** per una risorsa critica.
In altre parole, gestire l'accesso ad una risorsa critica tramite l'utilizzo di **variabili mutex**.

Un processo, nel mentre che non sta facendo istruzioni critiche (non sta accedendo a regioni critiche) , **non può bloccare un'altro processo**.

Nessun processo deve aspettare all'infinito per accedere una regione critica. al massimo, deve essere ucciso.


## Busy waiting

Mettere un processo su una variabile, che rimane continuamente (**occupando il processore**) in attesa di un interrupt.
Questa tecnica funziona, ma comporta molti problemi al PC (consumo processore -> consumo batteria).

Gli interrupt possono essere disabilitati, però dovrebbero essere SOLO disabilitati dai processi che accedono ad una risorsa critica, NON dall'utente. Ciò, infatti, comporta **molti rischi**.


### Alternanza stretta

Per **alternanza stretta** si intende **sincronizzazione del lavoro** tra due processi (es. un processo produce una risorsa che viene utilizzata da un altro processo).

*Esempio*: Una variabile è condivisa tra due thread per vedere chi può accedere ad una regione critica, e chi no.

Un **lock** che usa un busy waiting si chiama **spin lock**.


### Istruzione TSL
L'Istruzione  **TSL** è una istruzione assembly che permette di settare e modificare una variabile lock.
L'istruzione del TSL permette di **lockare** una variabile per indicare che un altro processo  sta usando la regione critica.
La TSL può essere vista come l'unione di **due istruzioni**.
-  Copia il valore del lock nel registro.
- Il valore del lock viene poi cambiato in 1, per indicare che ora **un processo sta usando una risorsa critica**, e perciò nessun'altro processo può accedervi.

 Se prima la lock era *0*, allora viene negato l'accesso alla risorsa critica da parte di altri processi.
 Termiato l'accesso alla regione critica del processo, il valore della lock che viene copiato nel registro è *1*, andando ad indicare che **la risorsa è libera di essere acceduta**