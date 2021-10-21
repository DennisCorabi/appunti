# Wireless transmission

## Introduzione

per comunicazione wireless si intende la trasmissione in radiofrequenza utilizzando onde elettromagnetiche.


## Onde elettromagnetiche


Quando gli elettroni si muovono, creano **onde elettromagnetiche** che possono essere propagate nello spazio.

Sono state ipotizzate dapprima da **James Clerk Maxwell** e vennero osservate per la prima volta, qualche anno dopo, dallo scienziato tedesco **Heinrich Hertz**.

**Proprietà di un onda**
1) Il numero di oscillazioni per secondo di un' onda si chiama **frequenza** $f$, ed è misurata in $Hz$.
2) La distanza tra due picchi massimi (o minimi) consecutivi di un onda è chiamata **lunghezza d'onda**, la cui unità di misura è il lambda [$\lambda$].
3) Tutte onde elettromagnetiche nel vuoto viaggiano alla stessa velocità, questa velocità è chiamata **velocità della luce** $c$, che corrisponde a circa $3 * 10^8$ m/sec.

**Relazione fondamentale:** $\lambda\times f=c$


**Trasmissione**
Quando una attenna viene collegata ad un circuito elettrico, le onde elettromagnetiche si **propagano** efficacemente e possono raggiungere distanze notevoli.
Questo è il principio alla base del sistema di **comunicazione senza fili**.

## Spettro elettromagnetico

Lo **spettro elettromagnetico** è l'insieme di tutte le possibili frequenze della radiazione elettromagnetica. 
Le onde dello spettro elettromagnetico possono essere utilizzate per trasmettere informazioni modulando la loro **ampiezza**, **frequenza** e **fase**.
Lo spettro elettromagnetico si divide in:
- **onde radio**
- **microonde**
- infrarossi
- **Ultra-Violetti**
- Raggi-X
- Gamma

Le onde **radio** e **microonde** vengono utlizzate per la comunicazione per cavi coassiali e twisted pair, nonchè per la radio FM e AM.
I **raggi UV** vengono invece utilizzati dalle fibre ottiche.

Le altre tipologie di onde (infrarossi, X,gamma) non vengono utilizzate a causa dei loro **svantaggi** (non passano attraverso le superfici, sono troppo instabili), a discapito dei loro **vantaggi** (maggiore frequenza -> maggiore MDR). 

### Metodi di comunicazione

**Frequency Hopping**
Il frequency hopping è un metodo di trasmissione dati caratterizzato da un continuo "saltare" di frequenza in frequenza.

Viene utilizzato prevalentemente nella comunicazione militare così da non farsi intercettare le comunicazioni.

**	TODO**




#### Radio Transmission

Le radio AM usano le bande MF.
A basse frequenze le onde attraversano bene gli ostacoli, ma la potenza diminuisce bruscamente con la distanza dalla sorgente, almeno alla velocità di $1/r^2$ nell'aria, poiché l'energia del segnale viene distribuita in modo più sottile su una superficie più ampia.

Questa attenuante si chiama **path loss**. Ad alte frequenze, le onde radio tendono a viaggiare in linee rette e a rimbalzare sugli ostacoli.


#### Trasmissione a microonde
sopra i 100 $Mhz$ le onde si spostano i linee rette e quindi possono essere concentrati in una linea con una piccola dispersione.

Vi sono alcune frequenze dove il tempo atmosferico fa la differenza.
nelle frequenze a $4GHz$, l'acqua riesce ad *assorbire* facilemente il segnale.
Questo per i segnali di comunicazione è un problema importantissimo.

## Politica di segnale
- Alcune frequenze sono riservate ed utilizzate

- Zone ISN (INDUSTRIAL, SCIENTIFIC, MEDICAL):
	frequenze libere a tutti quanti a patto che vengano utilizzate potenze di trasmissione molto basse, così da non creare interferenze agli altri.









