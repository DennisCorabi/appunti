# Stati di un processo

## Stati di un processo 

### Execute  

il programma si trova nella RAM e le sue istruzioni sono prelevate ed eseguite dalla CPU. 

### Ready  

processi che si trovano nella lista dei processi pronti per essere eseguiti che stanno aspettando il loro turno per entrare nella RAM (sei in attesa del processore) 

### Blocked 

Processo bloccato a causa di una chiamata di sistema (sei in attesa di una risorsa che ti deve dare l'OS). 

Dopo aver ottenuto la risorsa che gli serviva, il processo rientra nello stato di **Ready** per aspettare nuovamente il suo turno. 

Per essere bloccato, un processo deve essere prima in fase di esecuzione (execute). 

### Zombie

Un processo zombie è un processo finito, le cui risorse sono state riprese dall'OS, ma che occupa ancora un **PID nella RAM**. Effettivamente un morto vivente. 

Per essere Zombie, un processo deve essere prima in fase di esecuzione. 

Un processo Zombie si crea quando un processo figlio termina dopo il processo padre e quindi non ritorna a nessun processo il suo "return code" e rimane nella RAM. 

#### Comando 
Kill -signal <$PID$> (uccidere un processo solo tra quelli creati dall'utente che invoca il comando). 
***

## Misc
### Handler 

Gestisce il cambio di stato dei processi in concomitanza con degli specifici eventi. 

"se succede evento X, allora faccio l'istruzione Y." 

### Malloc (**M**emory **ALLOC**ation) 
Funzione che permette di "riservare" dello spazio in memoria RAM.
A tal proposito, l'argomento della funzione è la memoria da riservare espressa in **Byte**.

### Free
Opposto della Malloc, permette ad un processo di rilasciare le sue risorse in memoria. 
### Wait
Permette ad un processo di aspettare un segnale specifico o il termine di un altro processo prima di cambiare stato.
***