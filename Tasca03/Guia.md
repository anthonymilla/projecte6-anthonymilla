# MISSIÓ APACHE: DESPLEGAMENT MULTIDOMINI I SEGUR

| 1. Instal·lació i Configuració Base |
|----------------------------------------|

- Atureu i deshabiliteu el servei Apache2 per alliberar els ports 80 i 443.

Aturem i deshabilitem el servei Apache2 per alliberar els ports 80 i 443 amb les següents comandes (fem també amb now perquè ho faci en aquest moment).

```
sudo systemctl stop apache2
```

```
sudo systemctl disable apache2
```

```
sudo systemctl disable apache2 now
```

![- Atureu i deshabiliteu el servei Apache2 per alliberar els ports 80 i 443.
Aturem i deshabilitem el servei Apache2 per alliberar els ports 80 i 443 amb les següents comandes (fem també amb now perquè ho faci en aquest moment).](Img/Imatge01.png)

- Instal·leu el servidor web Nginx.

Instal·lem el servidor web Nginx amb la següent comanda:

```
sudo apt install nginx -y
```

![- Instal·leu el servidor web Nginx.
Instal·lem el servidor web Nginx amb la següent comanda:](Img/Imatge02.png)

- Verifiqueu que el servei està actiu i que la pàgina de benvinguda de Nginx es mostra correctament al navegador.

Verifiquem que el servei està actiu i que la pàgina de benvinguda de Nginx es mostra correctament al navegador:

![- Verifiqueu que el servei està actiu i que la pàgina de benvinguda de Nginx es mostra correctament al navegador.
Verifiquem que el servei està actiu i que la pàgina de benvinguda de Nginx es mostra correctament al navegador:](Img/Imatge03.png)

Perquè la pàgina de benvinguda de Nginx es mostri correctament editem el següent arxiu de configuració:

![Perquè la pàgina de benvinguda de Nginx es mostri correctament editem el següent arxiu de configuració:](Img/Imatge04.png)

![Perquè la pàgina de benvinguda de Nginx es mostri correctament editem el següent arxiu de configuració:](Img/Imatge05.png)

Editem la següent línia:

```
root /usr/share/nginx/html
```

![Editem la següent línia:](Img/Imatge06.png)

Comprovem la sintaxi i reiniciem el servei:

![Comprovem la sintaxi i reiniciem el servei:](Img/Imatge07.png)

![Comprovem la sintaxi i reiniciem el servei:](Img/Imatge08.png)

Fem ip a, bàsicament per veure l’ip i posar-la al navegador de la máquina zorin per fer la comprovació.

![Fem ip a, bàsicament per veure l’ip i posar-la al navegador de la máquina zorin per fer la comprovació.](Img/Imatge09.png)

Comprovem que la pàgina de benvinguda de Nginx es mostra correctament al navegador:

![Comprovem que la pàgina de benvinguda de Nginx es mostra correctament al navegador:](Img/Imatge10.png)

| 2. Configuració de Server Blocks (Multidomini) |
|----------------------------------------|

- Aprofiteu l'estructura de carpetes ja creada (/var/www/nexus i /var/www/academia). Si cal, ajusteu els permisos (propietari www-data).

Primerament ajustem els permisos (propietari www-data):

![- Aprofiteu l'estructura de carpetes ja creada (/var/www/nexus i /var/www/academia). Si cal, ajusteu els permisos (propietari www-data).
Primerament ajustem els permisos (propietari www-data):](Img/Imatge11.png)



![Hola](Img/Imatge12.png)

![Hola](Img/Imatge13.png)

![Hola](Img/Imatge14.png)

![Hola](Img/Imatge15.png)

![Hola](Img/Imatge16.png)

![Hola](Img/Imatge17.png)

![Hola](Img/Imatge18.png)

![Hola](Img/Imatge19.png)

![Hola](Img/Imatge20.png)

![Hola](Img/Imatge21.png)

![Hola](Img/Imatge22.png)

![Hola](Img/Imatge23.png)

![Hola](Img/Imatge24.png)

![Hola](Img/Imatge25.png)

![Hola](Img/Imatge26.png)

![Hola](Img/Imatge27.png)

![Hola](Img/Imatge28.png)

![Hola](Img/Imatge29.png)

![Hola](Img/Imatge30.png)

[Anar a l'enunciat](../Tasca03/README.md)  
[Anar a la pàgina inicial](../README.md)

