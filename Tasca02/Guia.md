# MISSIÓ APACHE: DESPLEGAMENT MULTIDOMINI I SEGUR

Primerament mostrem les IPs d'ambdues màquines:

![Primerament mostrem les IPs d'ambdues màquines:](Img/Imatge001.png)

![Primerament mostrem les IPs d'ambdues màquines:](Img/Imatge002.png)

I la prova de connectivitat:

![I la prova de connectivitat:](Img/Imatge003.png)

![I la prova de connectivitat:](Img/Imatge004.png)

| 1. Instal·lació i Configuració Base |
|----------------------------------------|

- Instal·leu el servidor web Apache sobre la vostra màquina virtual Ubuntu Server.           
Comencem instal·lant les màquines i posant-les en xarxa NAT.           
Ara instal·lem el servei Apache:

```
sudo apt install apache2
```

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

Creem un arxiu index.html dins de cada carpeta.

![Creem un arxiu index.html dins de cada carpeta.](Img/Imatge061.png)

- Configureu dos VirtualHosts a /etc/apache2/sites-available/ fent servir com a
base l'arxiu de configuració per defecte.      
La base és ```000-default.conf``` (la captura le fet després de les creacions, que m’havia oblidat).

![- Configureu dos VirtualHosts a /etc/apache2/sites-available/ fent servir com a
base l'arxiu de configuració per defecte.      
La base és 000-default.conf (la captura le fet després de les creacions, que m’havia oblidat).](Img/Imatge071.png)

I copiem.

![I copiem.](Img/Imatge072.png)

![I copiem.](Img/Imatge073.png)

Entrem als dos arxius i fem els canvis corresponents. 

![Entrem als dos arxius i fem els canvis corresponents.](Img/Imatge08.png)

Que en aquest cas serien aquestes línies:

```
ServerName www.academia.test
ServerAdmin webmaster@localhost
DocumentRoot /var/www/academia.test
```

![Que en aquest cas serien aquestes línies:](Img/Imatge09.png)

Ara el següent arxiu: 

![Ara el següent arxiu:](Img/Imatge10.png)

I les següents línies:

```
ServerName www.projectenexus.test
ServerAdmin webmaster@localhost
DocumentRoot /var/www/projectenexus.test
```

![Ara el següent arxiu:](Img/Imatge11.png)

- Activeu els llocs amb la comanda a2ensite i modifiqueu l'arxiu hosts per simular la resolució de noms (DNS) i que els dominis responguin correctament.        
Ara activem els llocs amb les següents comandes i seguidament modifiquem l'arxiu de hosts i fem les comprovacions corresponents:

![- Activeu els llocs amb la comanda a2ensite i modifiqueu l'arxiu hosts per simular la resolució de noms (DNS) i que els dominis responguin correctament.        
Ara activem els llocs amb les següents comandes i seguidament modifiquem l'arxiu de hosts i fem les comprovacions corresponents:](Img/Imatge12.png)

![- Activeu els llocs amb la comanda a2ensite i modifiqueu l'arxiu hosts per simular la resolució de noms (DNS) i que els dominis responguin correctament.        
Ara activem els llocs amb les següents comandes i seguidament modifiquem l'arxiu de hosts i fem les comprovacions corresponents:](Img/Imatge13.png)

Entrem a l'arxiu /etc/hosts

```
sudo nano /etc/hosts
```

![Entrem a l'arxiu /etc/hosts](Img/Imatge14.png)

Fem ```ip a``` per veure l'ip.

![Fem ip a per veure l'ip.](Img/Imatge15.png)

I posem l'ip i el nom dels dos directoris:

![I posem l'ip i el nom dels dos directoris:](Img/Imatge16.png)

Fem les comprovacions.

![Fem les comprovacions.](Img/Imatge17.png)

![Fem les comprovacions.](Img/Imatge18.png)

| 3. Personalització d'Errors |
|----------------------------------------|

Configureu una pàgina d'error personalitzada pel codi 404 (Not Found) per a, com a mínim, un dels VirtualHosts. El missatge ha de ser corporatiu i professional, evitant la pàgina per defecte del servidor.       
Configurem una pàgina d’error personalitzada pel codi 404:

![Configurem una pàgina d’error personalitzada pel codi 404:](Img/Imatge19.png)

I posem el següent missatge en aquest cas (El típic missatge: Pàgina no encontrada/Not Found), sense accents, ja que si no després surt malament el text:

![I posem el següent missatge en aquest cas (El típic missatge: Pàgina no encontrada/Not Found), sense accents, ja que si no després surt malament el text:](Img/Imatge20.png)

Reiniciem el servei.

![Reiniciem el servei.](Img/Imatge21.png)

I ara fem el mateix amb l’altre com podem veure:

![I ara fem el mateix amb l’altre com podem veure:](Img/Imatge22.png)

![I ara fem el mateix amb l’altre com podem veure:](Img/Imatge23.png)

![I ara fem el mateix amb l’altre com podem veure:](Img/Imatge24.png)

Entrem als arxius conf tant de projectenexus com de academia:

![Entrem als arxius conf tant de projectenexus com de academia:](Img/Imatge25.png)

I afegim la següent línia corresponent:

```
ErrorDocument 404 /404.html
```

Quedaria així:

```
ErrorLog ${APACHE_LOG_DIR}/error.log
CustomLog ${APACHE_LOG_DIR}/access.log combined
ErrorDocument 404 /404.html
```

![I afegim la següent línia corresponent:](Img/Imatge26.png)

Reiniciem el servei.

![Reiniciem el servei.](Img/Imatge27.png)

Ara entrem a l’altre arxiu, el de academia:

![Ara entrem a l’altre arxiu, el de academia:](Img/Imatge28.png)

I afegim la mateixa línia que abans:

```
ErrorDocument 404 /404.html
```

Quedaria així:

```
ErrorLog ${APACHE_LOG_DIR}/error.log
CustomLog ${APACHE_LOG_DIR}/access.log combined
ErrorDocument 404 /404.html
```

![I afegim la mateixa línia que abans:](Img/Imatge29.png)

Reiniciem el servei de nou.

![Reiniciem el servei de nou.](Img/Imatge30.png)

Després anem a la màquina Zorin, fem les comprovacions corresponents i com podem veure surten els missatges corresponents a cadascuna:

![Després anem a la màquina Zorin, fem les comprovacions corresponents i com podem veure surten els missatges corresponents a cadascuna:](Img/Imatge31.png)

![Després anem a la màquina Zorin, fem les comprovacions corresponents i com podem veure surten els missatges corresponents a cadascuna:](Img/Imatge32.png)

| 4. Seguretat i Certificats (HTTPS) |
|----------------------------------------|

- Habiliteu el mòdul SSL a Apache.        
El que fem és copiar l’arxiu TLS per defecte.

![- Habiliteu el mòdul SSL a Apache.        
El que fem és copiar l’arxiu TLS per defecte.](Img/Imatge33.png)

![- Habiliteu el mòdul SSL a Apache.        
El que fem és copiar l’arxiu TLS per defecte.](Img/Imatge34.png)

![- Habiliteu el mòdul SSL a Apache.        
El que fem és copiar l’arxiu TLS per defecte.](Img/Imatge35.png)



![Comprovacions.](Img/Imatge36.png)

![Comprovacions.](Img/Imatge37.png)

![Comprovacions.](Img/Imatge38.png)

![Comprovacions.](Img/Imatge39.png)

![Comprovacions.](Img/Imatge40.png)

![Comprovacions.](Img/Imatge41.png)

![Comprovacions.](Img/Imatge42.png)

![Comprovacions.](Img/Imatge43.png)

![Comprovacions.](Img/Imatge44.png)

![Comprovacions.](Img/Imatge45.png)

[Anar a l'enunciat](../Tasca02/README.md)  
[Anar a la pàgina inicial](../README.md)
