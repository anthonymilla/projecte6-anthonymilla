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

- Configureu dos Server Blocks (l'equivalent a VirtualHosts a Nginx) a /etc/nginx/sites-available/.

A la carpeta ```/etc/nginx/sites-available``` tenim l’arxiu del servidor per defecte default, la cual utilitzarem com plantilla per crear els nostres propis per això el que fem és copiar aquest arxiu per crear els dos que necessitem dins de la carpeta sites-available.

![- Configureu dos Server Blocks (l'equivalent a VirtualHosts a Nginx) a /etc/nginx/sites-available/.
A la carpeta /etc/nginx/sites-available tenim l’arxiu del servidor per defecte default, la cual utilitzarem com plantilla per crear els nostres propis per això el que fem és copiar aquest arxiu per crear els dos que necessitem dins de la carpeta sites-available.](Img/Imatge12.png)

Configurem dos Server Blocks (l'equivalent a VirtualHosts a Nginx) a /etc/nginx/sites-available/ corresponentment:

![Configurem dos Server Blocks (l'equivalent a VirtualHosts a Nginx) a /etc/nginx/sites-available/ corresponentment:](Img/Imatge13.png)

```
server {
        listen 80;
        listen [::]:80;
```

```
root /var/www/projectenexus.test;
```

```
server_name www.projectenexus.test.test;
```

![Configurem dos Server Blocks (l'equivalent a VirtualHosts a Nginx) a /etc/nginx/sites-available/ corresponentment:](Img/Imatge14.png)

Reiniciem el servei

![Reiniciem el servei](Img/Imatge15.png)

![Configurem dos Server Blocks (l'equivalent a VirtualHosts a Nginx) a /etc/nginx/sites-available/ corresponentment:](Img/Imatge16.png)

```
server {
        listen 80;
        listen [::]:80;
```

```
root /var/www/academia.test;
```

```
server_name www.academia.test.test;
```

![Configurem dos Server Blocks (l'equivalent a VirtualHosts a Nginx) a /etc/nginx/sites-available/ corresponentment:](Img/Imatge17.png)

![Configurem dos Server Blocks (l'equivalent a VirtualHosts a Nginx) a /etc/nginx/sites-available/ corresponentment:](Img/Imatge18.png)

- Creeu els enllaços simbòlics a sites-enabled/ per activar les configuracions.          
Verifiqueu la sintaxis amb nginx -t abans de reiniciar el servei.

Creem els enllaços simbòlics a sites-enabled/ per activar les configuracions i seguidament verifiquem la sintaxis amb nginx -t i després d’això reiniciem el servei.

![- Creeu els enllaços simbòlics a sites-enabled/ per activar les configuracions.          
Verifiqueu la sintaxis amb nginx -t abans de reiniciar el servei.
Creem els enllaços simbòlics a sites-enabled/ per activar les configuracions i seguidament verifiquem la sintaxis amb nginx -t i després d’això reiniciem el servei.](Img/Imatge19.png)

![- Creeu els enllaços simbòlics a sites-enabled/ per activar les configuracions.          
Verifiqueu la sintaxis amb nginx -t abans de reiniciar el servei.
Creem els enllaços simbòlics a sites-enabled/ per activar les configuracions i seguidament verifiquem la sintaxis amb nginx -t i després d’això reiniciem el servei.](Img/Imatge20.png)

Ara editarem l’arxiu /etc/nginx/nginx.conf i activem la següent linia, això per evitar problemes de memòria quan es treballa amb diversos noms.

![Ara editarem l’arxiu /etc/nginx/nginx.conf i activem la següent linia, això per evitar problemes de memòria quan es treballa amb diversos noms.](Img/Imatge21.png)

```
server_names_hash_bucket_size 64;
```

![Ara editarem l’arxiu /etc/nginx/nginx.conf i activem la següent linia, això per evitar problemes de memòria quan es treballa amb diversos noms.](Img/Imatge22.png)

Verifiquem la sintaxis amb nginx -t i després d’això reiniciem el servei.

![Verifiquem la sintaxis amb nginx -t i després d’això reiniciem el servei.](Img/Imatge23.png)

Comprovem la IP de l’arxiu /etc/hosts de la màquina Zorin.

```
sudo nano /etc/hosts
```

![Comprovem la IP de l’arxiu /etc/hosts de la màquina Zorin.](Img/Imatge24.png)

| 3. Personalització d'Errors |
|----------------------------------------|

- Configureu la directiva error_page 404 dins del bloc de servidor corresponent.


![Hola](Img/Imatge25.png)

![Hola](Img/Imatge26.png)

![Hola](Img/Imatge27.png)

![Hola](Img/Imatge28.png)

![Hola](Img/Imatge29.png)

![Hola](Img/Imatge30.png)

![Hola](Img/Imatge31.png)

![Hola](Img/Imatge32.png)

![Hola](Img/Imatge33.png)

![Hola](Img/Imatge34.png)

![Hola](Img/Imatge35.png)

![Hola](Img/Imatge36.png)

![Hola](Img/Imatge37.png)

![Hola](Img/Imatge38.png)

![Hola](Img/Imatge39.png)

![Hola](Img/Imatge40.png)

[Anar a l'enunciat](../Tasca03/README.md)  
[Anar a la pàgina inicial](../README.md)

