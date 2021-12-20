# Processi

## Threads
I **thread** 

///


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

### Terminare un Thread

I thread possono essere terminati utilizzando la funzione *pthread_exit*, dove mando una richiesta al thread di **suicidarsi**.


## Problemi tra i thread
**Zone critiche**: regioni in comune con i thread (es. variabili globali)
**corse critiche**: funzioni che utilizzano risorse critiche (condivise tra i vari thread)
**risorsa critica**: Variabile globale utilizzata dai thread scrivibile e leggibile.

Per evitare problemi di lettura/scrittura di una risorsa critica tra più thread, si instaura un "semaforo", che indica ad un thread se si può accedere alla variabile.
- Se è "**verde**": si può leggere la variabile (dal verde passa al rosso)
- Se è ""**rosso**"": aspetto fino a quando la risorsa ritorna disponibile.

I semafori possono essere implementati in una programma  in C utilizzando le variabili **Mutex**.

### Mutex

le variabili **Mutex** (**Mut**ual **ex**clusion) vietano a due o più thread di accedere ad una variabile contemporaneamente.
In C, le variabii mutex sono chiamate *pthread_mutex_t*.
Per **ogni variabile critica** ci deve essere una variabile mutex associata.

Se vi è una variabile mutex, la probabilità **corse critiche** si annulla (non ci possono essere errori).










