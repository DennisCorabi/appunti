# Multiplexing

## Time Division Multiplexing (TDM)

per tutti le stazioni, ognuna potrà usare il canale nella sua interezza per un certo lasso di tempo.
Il tempo viene quindi diviso tra i vari utilizzatori del canale.

## Frequency Division Multiplexing (FDM)

Il canale di  comunicazione viene diviso tra i vari utilizzatori del canale, ognuno dei quali avrà un certo range di frequenze che può utilzzare.
ad esempio, il **Wifi 2.4 GHz** utilizza questa tecnica per soddisfare tutti gli utilizzatori del canale, dando per ognuno **22 Mhz** di banda.

### Funzionamento

Un canale di comunicazione viene divisio in più piccoli canali grazie al filtraggio delle frequenze con il filtro **banda passante**.
Esso è un unione tra il filtro **passa alto** e il **filtro passa basso**, creando quindi un filtro che non fa passare le frequenze sotto un certo valore e sopra un certo valore.


## Code Division Multiplexing (CDM)

Questo sistema permette a più stazioni la **stessa frequenza** nello **stesso lasso di tempo** grazie all'utilizzo di un **identificatore**, associato in modo univoco ad una sola stazione (**NIC**).
Ad ogni stazione **NON** viene associata una sequenza di 0 e 1, bensì, per ragioni matematiche, di **1 e -1**.


### Simboli del canale

-  ** 0**: non sto inviando nessun bit
- **1/1**:  in sequenza, una stazione usa il canale.



### Funzionamento 

Se ad un canale A viene assegnata una sequenza di **chip** pari a *(-1,-1-1,1,1-1,1,1)*, allora invia un 1 se nel segnale viene inviata questa sequenza, 0 se il invia il complemento di questa sequenza (*1,1,1,-1,-1,1,-1,-1)*.	


### Comunicazioni ortogonali

Per poter comunicare contemporaneamente, due o più stazioni devono avere due sequenze di chip **ortogonali**, ovvero il loro prodotto scalare deve essere pari a **0**.

#### Esempio
Comunicazione tra **TRE** stazioni:

DATI
*B (+,++,+)	----B^(-,-,-,-)*
*C(+,-,-,+)---- C^(-,+,+,-)*
*D(+,+,-,-)----D^(-,-,+,+)*

 *BC=0*
*BD=0*
*CD=?*

$$ B*C = (1*1)+(1*-1)+(1*-1)+(1*1) = 1-1-1+1 = 0$$
$$ B*D = (1*1)+(1*1)+(1*-1)+(1*-1) = 1+1-1-1 = 0$$
$$ C*D = (1*1)+(1*-1)+(-1*-1)+(1*-1) = 1-1+1-1 = 0$$


*C - B - D* : sono tre stazioni le cui sequenze di chips sono **ortogonali** e perciò possono comunicare fra loro contemporaneamente.

	


