# MISSIÓ APACHE: DESPLEGAMENT MULTIDOMINI I SEGUR

| 1. Instal·lació i Configuració Base |
|----------------------------------------|

- Instal·leu el servidor web Apache sobre la vostra màquina virtual Ubuntu Server.           
Comencem instal·lant les màquines i posant-les en xarxa NAT.           
Ara instal·lem el servei Apache:

![- Instal·leu el servidor web Apache sobre la vostra màquina virtual Ubuntu Server.           
Comencem instal·lant les màquines i posant-les en xarxa NAT.           
Ara instal·lem el servei Apache:](Img/Imatge01.png)

- Verifiqueu el funcionament del servei utilitzant la comanda apachectl per comprovar l'estat.           
Comprovem l’estat.

![- Verifiqueu el funcionament del servei utilitzant la comanda apachectl per comprovar l'estat.           
Comprovem l’estat.](Img/Imatge02.png)

- Assegureu-vos que l'usuari www-data s'ha creat correctament i verifiqueu els
permisos de la carpeta /var/www.

![- Assegureu-vos que l'usuari www-data s'ha creat correctament i verifiqueu els
permisos de la carpeta /var/www.](Img/Imatge03.png)

Comprovació de /var/www i /var/www/html

![Comprovació de /var/www i /var/www/html](Img/Imatge04.png)

Comprovacions.

![Comprovacions.](Img/Imatge05.png)

| 2. Desplegament de VirtualHosts (Multidomini) |
|----------------------------------------|

- El client té dos dominis: projectenexus.test (Site 1) i academia.test (Site 2).
- Creeu l'estructura de directoris necessària a /var/www/ per allotjar ambdós llocs per separat de manera organitzada.

![-El client té dos dominis: projectenexus.test (Site 1) i academia.test (Site 2).
Creeu l'estructura de directoris necessària a /var/www/ per allotjar ambdós llocs per separat de manera organitzada.](Img/Imatge06.png)

![-El client té dos dominis: projectenexus.test (Site 1) i academia.test (Site 2).
Creeu l'estructura de directoris necessària a /var/www/ per allotjar ambdós llocs per separat de manera organitzada.](Img/Imatge07.png)

- Configureu dos VirtualHosts a /etc/apache2/sites-available/ fent servir com a
base l'arxiu de configuració per defecte.      
Entrem als dos arxius i fem els canvis corresponents. 

![- Configureu dos VirtualHosts a /etc/apache2/sites-available/ fent servir com a
base l'arxiu de configuració per defecte.      
Entrem als dos arxius i fem els canvis corresponents.](Img/Imatge08.png)

Que en aquest cas serien aquestes línies:

```

```

![Que en aquest cas serien aquestes línies:](Img/Imatge09.png)

Ara el següent arxiu: 

![Ara el següent arxiu:](Img/Imatge10.png)

![Ara el següent arxiu:](Img/Imatge11.png)

- Activeu els llocs amb la comanda a2ensite i modifiqueu l'arxiu hosts per simular la resolució de noms (DNS) i que els dominis responguin correctament.        
Ara activem els llocs amb les següents comandes i seguidament modifiquem ‘arxiu de hosts i fem les comprovacions corresponents:

![- Activeu els llocs amb la comanda a2ensite i modifiqueu l'arxiu hosts per simular la resolució de noms (DNS) i que els dominis responguin correctament.        
Ara activem els llocs amb les següents comandes i seguidament modifiquem ‘arxiu de hosts i fem les comprovacions corresponents:](Img/Imatge12.png)

![- Activeu els llocs amb la comanda a2ensite i modifiqueu l'arxiu hosts per simular la resolució de noms (DNS) i que els dominis responguin correctament.        
Ara activem els llocs amb les següents comandes i seguidament modifiquem ‘arxiu de hosts i fem les comprovacions corresponents:](Img/Imatge13.png)

![- Activeu els llocs amb la comanda a2ensite i modifiqueu l'arxiu hosts per simular la resolució de noms (DNS) i que els dominis responguin correctament.        
Ara activem els llocs amb les següents comandes i seguidament modifiquem ‘arxiu de hosts i fem les comprovacions corresponents:](Img/Imatge14.png)

![- Activeu els llocs amb la comanda a2ensite i modifiqueu l'arxiu hosts per simular la resolució de noms (DNS) i que els dominis responguin correctament.        
Ara activem els llocs amb les següents comandes i seguidament modifiquem ‘arxiu de hosts i fem les comprovacions corresponents:](Img/Imatge15.png)

![- Activeu els llocs amb la comanda a2ensite i modifiqueu l'arxiu hosts per simular la resolució de noms (DNS) i que els dominis responguin correctament.        
Ara activem els llocs amb les següents comandes i seguidament modifiquem ‘arxiu de hosts i fem les comprovacions corresponents:](Img/Imatge16.png)

![- Activeu els llocs amb la comanda a2ensite i modifiqueu l'arxiu hosts per simular la resolució de noms (DNS) i que els dominis responguin correctament.        
Ara activem els llocs amb les següents comandes i seguidament modifiquem ‘arxiu de hosts i fem les comprovacions corresponents:](Img/Imatge17.png)

![- Activeu els llocs amb la comanda a2ensite i modifiqueu l'arxiu hosts per simular la resolució de noms (DNS) i que els dominis responguin correctament.        
Ara activem els llocs amb les següents comandes i seguidament modifiquem ‘arxiu de hosts i fem les comprovacions corresponents:](Img/Imatge18.png)

| 3. Personalització d'Errors |
|----------------------------------------|

Configureu una pàgina d'error personalitzada pel codi 404 (Not Found) per a, com a mínim, un dels VirtualHosts. El missatge ha de ser corporatiu i professional, evitant la pàgina per defecte del servidor.



![Comprovacions.](Img/Imatge19.png)

![Comprovacions.](Img/Imatge20.png)

![Comprovacions.](Img/Imatge21.png)

![Comprovacions.](Img/Imatge22.png)

![Comprovacions.](Img/Imatge23.png)

[Anar a l'enunciat](../Tasca02/README.md)  
[Anar a la pàgina inicial](../README.md)
