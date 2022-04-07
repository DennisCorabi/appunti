# Network layer

**Indirizzo IPv4**: composto da 32 bit divisi in 4 byte.
Un router dovrebbe almeno avere due schede di rete (con IP diversi).

**Inet**:  indirizzo IPv4 (127.0.0.1/8 per loopback)
**Inet6**:  indirizzo IPv6 ( : : 1/128 per loopback)

***
#### Indirizzi IPv4

###### Categorie

divisi in **classe A**, **classe B** e **classe C**
- *Classe A*: netmask di 8 bit --> 255.0.0.0. Un indirizzo di classe A **deve incominicare con un bit a 0**.
- *Classe B*: netmask di 16 bit --> 255.255.0.0. Un indirizzo di classe B **deve avere il secondo bit a 0**.
- *Classe C*: netmask di 24 bit --> 255.255.255.0. Un indirizzo di classe C **deve avere il secondo bit a 1**

Tutti gli indirizzi che incominciano con uno 0 o il 127 sono riservati.
**Classful addressing**:  l'indirizzo con una manciata di bit che permettono di rilevare il tipo dell'indirizzo IPv4 in questione.

**Subnetting**: prendere una rete più grande e dividerla in reti più piccole. creare subnet.
**Supernetting**: prendere reti più piccole e unire in una più grande.

###### Indirizzi pubblici e privati 
**Indirizzo pubblico**: indirizzo di un client o server che vuole essere raggiungibile da internet.
**Indirizzo privato**: indirizzo di un host appertenente ad una LAN. Tra gli indirizzi privati sono presenti degli indirizzi 

**CIDR** (**C**lassess **I**nter**D**omain **R**outing): possiamo usare un numero di bit a piacere per comporre la netmask. solitamente questo non è possibile perchè vengono accettati solo valori standard (8,16,24 bit).

***


