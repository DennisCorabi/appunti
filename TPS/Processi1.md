
# Processi

## Parti di un processo
Composto da tre parti: 

-   **code segment**: statico, contiene le istruzioni del programma (read only nella maggior parte dei casi).  
-   **Stack segment**: dinamico, contiene variabili locali, informazioni di stato, tutti i registri, etc.. (read-write) 
-   **Data segment**: dinamico, contiene le variabili globali, statiche e dinamiche (read-write). 
    
### Processo dinamico
può cambiare la sua dimensione a run-time (sotto previa approvazione 
dell'OS). 
***
## Memoria Virtuale 

Tutta la memoria disponibile del sistema è chiamata memoria virtuale,  ed è la somma della **RAM + SWAP** (porzione del disco che simula il funzionamento della RAM). 

La memoria virtuale viene gestita dalla **MMU** (parte interna al processore), che trasforma gli indirizzi virtuali in indirizzi fisici. 
Se un processo tenta di scrivere in un code segment, la MMU avvia un interrupt che informa l'OS dell'accaduto, il quale poi lo uccide. 
***
## Thread
Un thread è una parte di un processo.
Ogni processo ha almeno un thread (ovvero il processo stesso) e può crearne altri. 
Dal punto di vista dell'OS, due o più thread di un processo sono visti come solo uno. 

Due thread, per essere parte dello processo, devono avere il **code e il data segment in comune**. 
Hanno quindi variabili locali diverse e variabili di stato diverse (stack segment diverso). 
***
## Clone & Fork

### Clone
Un processo crea un figlio mandando la chiamata di sistema **CLONE** all' OS, creando un processo esattamente uguale al processo madre (segmenti uguali ,all'inizio condividono pure lo stesso data segment). 

Il sistema operativo riesce ad identificarli solo grazie al **PID**, **univoco** per ogni processo. 

### Fork
Essendo CLONE una chiamata di sistema scomoda, viene utilizzata la **FORK**. 

La FORK permette ad un processo creare un processo figlio identico al padre (stessi segmenti, stesso program counter), il quale poi manda una chiamata al sistema per caricare un altro processo. 

Il processo padre conosce il PID del figlio, mentre non avviene viceversa. 

In un programma dove vengono creati dei processi con FORK, se pid=0 allora è il figlio, pid!=0 allora è il padre. 

#### Limitazioni della Fork
Il sistema permette di limitare ciò che l'utente può fare (creare troppi processi, scrivere un file di grandi dimensioni su disco, etc..) grazie alle funzioni della libreria Ulimit. 

Se si eseguono troppe FORK, ovvero se si creano troppi processi, il sistema diventa inutilizzabile e l'OS rifiuta ulteriori FORK. 
***

