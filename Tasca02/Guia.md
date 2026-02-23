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

![Comprovacions.](Img/Imatge06.png)

![Comprovacions.](Img/Imatge07.png)

- Configureu dos VirtualHosts a /etc/apache2/sites-available/ fent servir com a
base l'arxiu de configuració per defecte.      
Entrem als dos arxius i fem els canvis corresponents. 

![Comprovacions.](Img/Imatge08.png)

Que en aquest cas serien aquestes línies:

```

```

![Comprovacions.](Img/Imatge09.png)

Ara el següent arxiu: 

![Comprovacions.](Img/Imatge10.png)

![Comprovacions.](Img/Imatge12.png)

- Activeu els llocs amb la comanda a2ensite i modifiqueu l'arxiu hosts per simular la resolució de noms (DNS) i que els dominis responguin correctament.        
Ara activem els llocs amb les següents comandes i seguidament modifiquem ‘arxiu de hosts i fem les comprovacions corresponents:

![Comprovacions.](Img/Imatge13.png)

![Comprovacions.](Img/Imatge14.png)

![Comprovacions.](Img/Imatge15.png)

![Comprovacions.](Img/Imatge16.png)

![Comprovacions.](Img/Imatge17.png)

![Comprovacions.](Img/Imatge18.png)

![Comprovacions.](Img/Imatge19.png)

[Anar a l'enunciat](../Tasca02/README.md)  
[Anar a la pàgina inicial](../README.md)
