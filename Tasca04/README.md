# Introducció

Fins ara heu configurat dos servidors web diferents: el clàssic i robust Apache i el lleuger i ràpid Nginx. Aparentment, tots dos fan el mateix: mostrar les pàgines web del vostre client Nexus. Però, es comporten igual sota pressió?

En aquesta pràctica deixareu de banda la configuració i ens posareu el barret d'Auditors de Sistemes. Sotmetreu els vostres servidors a proves d'estrès (Benchmarking) des de la vostra màquina client (Zorin OS) per determinar quin dels dos gestiona millor les connexions. Això és clau a l’hora de presentar la vostra proposta al clients.

# Descripció de l'activitat

Cadascú de vosaltres haurà de disposar de la màquina virtual on teniu els servidors Apache i Nginx. El primer que caldrà fer és adaptar el contingut web perquè tinguin un aspecte més professional i permeti fer unes proves més realistes. Podeu usar la IA per generar una pàgina corporativa al site de nexus. Hauria de tenir imatges, estils, etc.
Un de vosaltres farà la prova sobre Apache i l’altre sobre Nginx, de manera que assegureu-vos de tenir habilitat en cada màquina el servei que correpongui.
El client serà un Zorin, al que caldrà que instal·leu les utilitats apache2-utils per terminal.

# Proves:

## Prova càrrega lleugera

Simulareu un trànsit normal. Imagineu que 10 usuaris estan navegant per la web simultàniament, generant 1000 peticions.

### Sintaxi de la comanda:

- ab -n [Total Peticions] -c [Usuaris Concurrents] [http://[IP_SERVIDOR]/](http://[IP_SERVIDOR]/)

Anoteu els següents valors pels dos servidors:

- Time taken for tests: (Temps total)
- Transfer Rate
- Requests per second: (Peticions per segon - quant més alt, millor)
- Time per request (mean): (Temps mitjà de resposta - quant més baix, millor)
- Completed request
- Failed request

## La prova d'estrès

Ara posareu els servidors al límit. Simularem que la vostra web s'ha fet viral o que esteu rebent un petit atac. Llançarem 10.000 peticions amb 100 usuaris simultanis colpejant el
servidor alhora.

ab -n 10000 -c 100 [http://192.168.](http://192.168.)X.XXX/

**Nota:** Si algun servidor falla (dona errors o "Connection timed out"), anoteu-ho. Això
també és un resultat!

Anoteu els resultats que obteniu igual que a la prova anterior.

# Què cal lliurar

Crear una taula comparativa amb les dades obtingudes:

| Mètrica | Apache prova lleugera | Nginx prova lleugera | Apache prova d’estrès | Nginx prova d’estrès |
|----------|------------------------|------------------------|-------------------------|------------------------|
| Time taken for test | | | | |
| Transfer rate | | | | |
| RPS | | | | |
| Time per request | | | | |
| Completed request | | | | |
| Failed request | | | | |

## Material de suport

J.D. Muñoz. El comando ab. Servicios de Red e Internet. 2017. Disponible a:
https://serviciosgs.readthedocs.io/es/latest/rendimiento/ab.html

[Anar a la Solució](../Tasca04/Solucio.md)    
[Anar a la pàgina inicial](../README.md)
