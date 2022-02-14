# CRC

**Cycling Redundancy Checks**: individua gli errori, non li corregge.
Faccio due CRC tra il frame nel mittente ed il frame del destinatario: controllo se i due CRC sono identici.
Il CRC è un **codice polinomiale** dove i coefficienti dei polinomi sono 0 o 1.

$$
x^3+5x^2-6x-1.5
$$
**isoformismo**: rappresentare una equazione come un vettore (1,5,-6,-1.5)

Abbiamo ora bisogno di un polinomio speciale, chiamato **polinomio generatore**.

frame costituito da una concatenazione di due stringhe: frame stesso (espresso come polinomio) ed il **polinomio generatore**.
Quest'ultima parte viene inserito nel fondo del frame e controlla che il **frame** **inviato e quello ricevuto siano identici**.
Per questo motivo, il polinomio deve essere definito prima dell'invio del messaggio e sarà identico sia per il frame del mittente che del destinatario.

Il grado del polinomio generatore **non può essere** maggiore del grado del polinomio del frame a cui è attaccato.


### Calcolo CRC
- Grado del polinomio generatore (costante) = *r*
- messaggio composto da *m* bit (payload del frame)
- Aggiungo il CRC a 0 (non lo abbiamo ancora definito)
- Moltiplico il frame per il polinomio generatore di grado *r*:  *M(x) x^r*
- Divido: divido il frame ampliato per il polinomio generatore
 
**Overhead**: spazio utilizzato dai bit di ridondanza che vengono aggiunti al frame per il controllo/correzione degli errori.
**Interleaving**: tramite speciali algoritmi, invio i bit del payload, dell'header e del trailer in modo sparso.


#### esercizio
G(x) = *x^3+1* --> r = *3* --> (1,0,0,1)
M(x) = *11010001101001*
M(x) * x^r = 1101000110**000** (tre bit aggiunti come il grado del polinomio generatore)

**Divido il frame amplificato per la sequenza del polinomio generatore**
Il primo elemento deve essere sempre 1.





