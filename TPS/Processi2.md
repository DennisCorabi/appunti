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
- 
- puntatore ad una funzione (puntatore alla prima istruzione di una funzione)

I thread possono a loro volta creare altri thread dal momento che **NON** vi è una gerarchia fra i thread.


### Terminare un Thread

I thread possono essere terminati utilizzando la funzione *pthread_exit*, dove mando una richiesta al thread di **suicidarsi**.








