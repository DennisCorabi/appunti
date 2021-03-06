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

***

### Tipologie di comunicazione

 #### Radio transmission
 
Le onde radio sono largamente utilizzate nella comunicazione wireless perchè  sono **facili da generare**, si **propagano su lunghe distanze** e possono **oltrepassare le pareti**.
Il ricevitore, inoltre, non deve essere perfettamente allineato al mittente grazie al fatto che le onde radio si disperdono in tutte le direzioni.

**Path Loss e tolleranza ai rumori**

A **basse frequenze** le onde attraversano bene gli ostacoli, ma la potenza diminuisce bruscamente con la distanza dalla sorgente poiché l'energia del segnale viene distribuita in modo **più sottile** su una superficie **più ampia**; Questa attenuante si chiama **path loss**. 

Ad **alte frequenze**, le onde radio tendono a viaggiare in linee rette e a rimbalzare sugli ostacoli.

Le onde radio ad alta frequenza, inoltre, vengono "**assorbite**" in parte dalla pioggia e dalla neve, e questo può provocare molti disagi.
A tutte le frequenze, poi, le onde radio subiscono l'interferenza di motori e strumenti elettrici.

**Tipologie**
le onde radio si distinguono in base alla loro frequenza in:
- Very Low Frequency (**VLF**)
- Low Frequency (**LF**)
- Medium Frequency (**MF**)
- High Frequency (**HF**)
- Very High Frequency (**VHF**)

le onde VLF,LF e MF **seguono il terreno** mentre le onde HF e VHF **rimbalzano** contro la ionosfera e ritornano sulla terra.

Le **radio AM** usano le bande MF.


#### Microwave Transmission

sopra i 100 $Mhz$ le onde si spostano in **linee rette** e quindi possono essere **concentrate** in una linea con una piccola dispersione.

Concentrare tutta l'energia del segnale su una antenna ricevitrice ci dà un maggiore **S/N** (ovvero maggiore MDR), ma bisogna **allineare perfettamente** l'antenna con il trasmettitore (a differenza delle onde radio).
Inoltre, i vari riceventi non si creano interferenza a vicenda grazie al fatto che le microonde non si disperdono.

**Tolleranza delle microonde**

Le microonde, a differenza delle onde radio, non passano attraverso le superfici e in alcuni strati dell'atmosfera possono persino essere **rallentate** o oppure **cancellate**.
Questo fenomento è gravissimo ed è chiamato **multipath fading**.

Vi sono poi alcune frequenze dove il tempo atmosferico fa la differenza; ad esempio, nelle frequenze a *4GHz*, l'acqua riesce ad **assorbire** facilemente il segnale.
Questo fenomeno per i segnali di comunicazione è un problema importantissimo tanto quanto lo è il multipath fading.

#### Politica di segnale dello spettro elettromagnetico

per prevenire il caos totale, i governi nazionali distribuiscono le varie frequenze tra le radio AM, radio FM, televisori, telefoni, eccetera.

Un agenzia internazionale la **ITU-R**, coordina l'allocazione di frequenze sui dispositivi cosicchè essi possano essere utilizzati anche in paesi diversi.

**Distribuzione delle freuquenze**
lo spettro elettromagnetico viene suddiviso tra i suoi utlizzatori:

- Alcune **frequenze** sono **riservate** ed utilizzate per scopi prevalentemente militari.
- **ISM** (Industrial, Scientific, Medical):
	frequenze libere a tutti quanti a patto che vengano utilizzate **potenze di trasmissione molto basse**, così da non creare interferenze agli altri utilizzatori di quel range di frequenze.
- **U-NII** (Unlicensed National Information Infrastucture): parte dello spettro magnetico a  *5GHz*, facende parte delle zone **ISN**, ancora sottosviluppato ma in continuo aumento di diffusione.
- **White Spaces** : parte dello spettro elettromagnetico a *700MHz* che è stato allocato ma che non viene utilizzato.

#### Infrared  Transmission

Le **trasmissioni ad infrarossi** sono largamente utilizzate per le brevi distanze.
Vengono utiizzate prevalentemente nei telecomandi, data la loro capacità di **rimbalzare sulle pareti**.
Non potendo creare delle interferenze significative , le trasmissioni ad infrarossi non sono regolamentate dai governi.
Sono dei segnali molto **economici** ed hanno una **bassa potenza**.

#### Light Transmission

La trasmissione utilizzando segnali di luce è monodirezionale (vi è un tramittente ed un ricevitore), ovvero **simplex**.
Questa tipologia di trasmissione conferisce un'**ampia larghezza di banda** per un **costo** relativamente **economico**.
Difficilmente crea interferenze (grazie al fatto che l'onda è pressochè dritta) ed è **facilmente installabile**.

D'altro canto, si deve far sì che il tramittore ed il ricevente siano **perfettamente allineati** (basta solo qualche grado di differenza che il segnale non arriva!).

Inoltre, vento, pioggia, neve, effetto morgana, posso modificare la traiettoria del fascio di luce, rendendo ancor più complicata la ricezione del segnale da parte del mittente.
***









