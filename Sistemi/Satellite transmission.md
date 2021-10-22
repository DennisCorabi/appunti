# Satellite transmission

 ## Introduzione
 
La comunicazione satellitare viene utilizzata per vari scopi grazie alle sue interessanti proprietà.

**Funzionamento** 
Un satellite può essere visto come un grande ripetitore di microonde nello spazio.
1. Dal trasmittore, il segnale microonde arriva al satellite in modo analogico.
2. I **transponder** all'interno del satellite lo trasformano i segnale digitale.
3. dopo averlo **amplificato**, il segnale viene **riconvertito** in segnale analogico
4. Il segnale viene **re-inviato** sulla terra con una **frequenza diversa**, così da non creare delle interferenze al segnale che sta arrivando al satellite.

Questa procedura è chiamata **bent pipe**.


## Come fanno a rimanere nello spazio?

I satelliti sono soggetti a **due forze**:
- **Forza Centripeta**: il satellite viene attratto verso il nucleo della terra, quindi viene "spinto" in basso (secondo la legge di Newton sulla gravità).
- **Forza Centrifuga**:il satellite appena lanciato nello spazio e per tutta la durata della sua vita, avrà un piccolo serbatoio che gli permette di **mettersi in moto** con una certa **velocità angolare** (ed una accellerazione centrifuga), il quale gli permette di rimanere in orbita ed eventualmente di aggiustare dei piccori errori di traettoria (**station keeping**)

Se la somma di queste due forze è zero, allora il satellite rimarrà nello spazio senza cadere sulla terra.

## Diverse tipologie di satellite

### Satelliti Geostazionari (GEO)

Secondo la legge di Keplero, i satelliti che si trova a circa **35.800 Km** dal nucleo della terra compiono un periodo attorno ad essa in circa **24 ore**.

Detto ciò, si può dire che i satelliti che si trovano a questa altitudine li vediamo **fermi** nel cielo perchè ruotano attorno al nucleo insieme a noi e ad alla medesia velocità: sono i **Satelliti Geostazionari**.

#### Caratteristiche

I satelliti geostazionari ruotano sopra l'equatore devono essere distanziati fra di loro di circa **due gradi** per non creare interferenze o, peggio ancora, eventuali collisioni.
Da ciò si evince che ci posso essere nello spazio sono **180** satelliti geostazionari.

D'altro canto, i **transponder** all'interno di questi satelliti possono operare su diverse frequenze ed aumentare quindi la larghezza di banda totale del satellite.

I satelliti geostazionari pesano oltre **5 tonnellate** e consumano moltissima potenza, la maggior parte della quale è ricavata dal raccogliemento dell'energia solare grazie a dei pannelli.

Anche se i segnali viaggiano ad una velocità elevatissima (velocità della luce *c*), sono soggetti a dei **rallentamenti** influenzati prevalentemente dalla **distanza** del satellite dal ricevente.

#### Latenza
La latenza è somma del tempo di volo del segnale (sia andata che ritorno) ed il tempo di **bent-pipe** (ovvero il tempo dove il segnale si trova nel satellite).
Da ciò si evince che le gli utilizzatori dei satelliti sull'equatore avranno una **minore latenza** di chi li usa in Europa come in Nord America.

Un vantaggio dell'utilizzo dei satelliti è che il costo di trasmissione del segnale è **indipendente** dalla tua distanza dal satellite.

**Sicurezza**
Sfortunatamente, i segnali inviati e ricevuti dal satellite possono essere facilemente intercettati e devono essere per forza criptati.




#### Station Keeping
Gli effetti di attrazione da parte della luna e del sole tendono a modificare l'orbita del satellite.
Per ovviare a questo problema, sono presenti all'interno del satellite dei motori atti a correggere la traiettoria del satellite.
Questa tecnica è chiamata **station keeping**.

#### Frequenze Satellitari e footprint
Per non interferire con gli utilizzatori di onde radio sulla terra, la ITU ha allocato alcune frequenze radio per la trasmissione **da** (**Downlink**) e **verso** (**uplink**) il satellite.

La **footprint** di un satellite geostazionario è la sua copertura della terra.
I primi satelliti geostazionari coprivano 1/3 dell'intero globo


#### Vsat (Very Small Aperture Terminals)

La tecnologia dei **VSAT** consiste nella presenza di piccoli terminali, alimentati ad un 1W di **potenza**, che trasmettono con 1	Mbps di **uplink** e **downlink** anch'esso nell'ordine dei Mbps.

Vengono solitamente utilizzati per le trasmissioni televisive **simplex**.

I terminali VSAT utilizzano poi delle speciali stazioni terrestri dotate di enormi antenne, chiamate **HUB**, che fungono da **mediatrici** tra il satellite ed il ricevente, **amplificando** il segnale ricevuto.

La tecnologia VSAT viene ampiamente utilizzata nei paesi dove non è possibile usufruire di tecnologie più costose.

### Satelliti MEO

ad altituidini più basse troviamo, comprese tra le due fasce di Van Allen, i **satelliti MEO** (Medium-Earth Orbit Satellites).
Trovandosi ad una più bassa altitudine (compresa tra i 5000 ed i 15000 Km), coprono una superficie più bassa di terra (minore **footprint**) e compiono una rotazione della terra in circa **6 ore**.

Sono molto più economici rispetto ai satelliti geostazionari per quanto riguarda il costo di manutenzione/installazione e per l'uso di carburante.

I satelliti in questa fascia sono circa **30** e fanno parte del **GPS** (Global Positioning System).


### Satelliti LEO

ad altitudini ancora più basse (fino a 1000 Km), troviamo i cosidetti satelliti LEO (Low-Earth Orbit Satellites).









 

