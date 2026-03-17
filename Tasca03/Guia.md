# MISSIÓ NGINX: MIGRACIÓ D'ALT RENDIMENT I ARQUITECTURA LLEUGERA

Primerament mostrem les IPs d'ambdues màquines:

![Primerament mostrem les IPs d'ambdues màquines:](Img/Imatge001.png)

![Primerament mostrem les IPs d'ambdues màquines:](Img/Imatge002.png)

I prova de connectivitat:

![I prova de connectivitat:](Img/Imatge003.png)

![I prova de connectivitat:](Img/Imatge004.png)

![I prova de connectivitat:](Img/Imatge005.png)

| 1. Preparació de l'Entorn i Instal·lació: |
|----------------------------------------|

- **Atureu i deshabiliteu el servei Apache2 per alliberar els ports 80 i 443.**

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

- **Instal·leu el servidor web Nginx.**

Instal·lem el servidor web Nginx amb la següent comanda:

```
sudo apt install nginx -y
```

![- Instal·leu el servidor web Nginx.
Instal·lem el servidor web Nginx amb la següent comanda:](Img/Imatge02.png)

- **Verifiqueu que el servei està actiu i que la pàgina de benvinguda de Nginx es mostra correctament al navegador.**

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

Fem ```ip a```, bàsicament per veure l’ip i posar-la al navegador de la máquina zorin per fer la comprovació.

![Fem ip a, bàsicament per veure l’ip i posar-la al navegador de la máquina zorin per fer la comprovació.](Img/Imatge09.png)

Comprovem que la pàgina de benvinguda de Nginx es mostra correctament al navegador:

![Comprovem que la pàgina de benvinguda de Nginx es mostra correctament al navegador:](Img/Imatge10.png)

| 2. Configuració de Server Blocks (Multidomini) |
|----------------------------------------|

- **Aprofiteu l'estructura de carpetes ja creada (/var/www/nexus i /var/www/academia). Si cal, ajusteu els permisos (propietari www-data).**

Aprofitem l'estructura de carpetes ja creada (/var/www/nexus i /var/www/academia). Primerament ajustem els permisos (propietari www-data):

![- Aprofiteu l'estructura de carpetes ja creada (/var/www/nexus i /var/www/academia). Si cal, ajusteu els permisos (propietari www-data).
Aprofitem l'estructura de carpetes ja creada (/var/www/nexus i /var/www/academia). Primerament ajustem els permisos (propietari www-data):](Img/Imatge11.png)

- **Configureu dos Server Blocks (l'equivalent a VirtualHosts a Nginx) a /etc/nginx/sites-available/.**

A la carpeta ```/etc/nginx/sites-available``` tenim l’arxiu del servidor per defecte default, la cual utilitzarem com plantilla per crear els nostres propis per això el que fem és copiar aquest arxiu per crear els dos que necessitem dins de la carpeta sites-available.

![- Configureu dos Server Blocks (l'equivalent a VirtualHosts a Nginx) a /etc/nginx/sites-available/.
A la carpeta /etc/nginx/sites-available tenim l’arxiu del servidor per defecte default, la cual utilitzarem com plantilla per crear els nostres propis per això el que fem és copiar aquest arxiu per crear els dos que necessitem dins de la carpeta sites-available.](Img/Imatge12.png)

Configurem dos Server Blocks (l'equivalent a VirtualHosts a Nginx) a ```/etc/nginx/sites-available/``` corresponentment:

![Configurem dos Server Blocks (l'equivalent a VirtualHosts a Nginx) a /etc/nginx/sites-available/ corresponentment:](Img/Imatge13.png)

Editem les següents línies:

```
server {
        listen 80;
        listen [::]:80;
```

```
root /var/www/projectenexus.test;
```

```
server_name www.projectenexus.test;
```

![Editem les següents línies:](Img/Imatge14.png)

Reiniciem el servei

![Reiniciem el servei](Img/Imatge15.png)

![Configurem dos Server Blocks (l'equivalent a VirtualHosts a Nginx) a /etc/nginx/sites-available/ corresponentment:](Img/Imatge16.png)

Editem les següents línies:

```
server {
        listen 80;
        listen [::]:80;
```

```
root /var/www/academia.test;
```

```
server_name www.academia.test;
```

![Editem les següents línies:](Img/Imatge17.png)

![Reiniciem el servei](Img/Imatge18.png)

- **Creeu els enllaços simbòlics a sites-enabled/ per activar les configuracions.          
Verifiqueu la sintaxis amb nginx -t abans de reiniciar el servei.**

Creem els enllaços simbòlics a ```sites-enabled/``` per activar les configuracions i seguidament verifiquem la sintaxis amb ```nginx -t``` i després d’això reiniciem el servei.

![- Creeu els enllaços simbòlics a sites-enabled/ per activar les configuracions.          
Verifiqueu la sintaxis amb nginx -t abans de reiniciar el servei.
Creem els enllaços simbòlics a sites-enabled/ per activar les configuracions i seguidament verifiquem la sintaxis amb nginx -t i després d’això reiniciem el servei.](Img/Imatge19.png)

![- Creeu els enllaços simbòlics a sites-enabled/ per activar les configuracions.          
Verifiqueu la sintaxis amb nginx -t abans de reiniciar el servei.
Creem els enllaços simbòlics a sites-enabled/ per activar les configuracions i seguidament verifiquem la sintaxis amb nginx -t i després d’això reiniciem el servei.](Img/Imatge20.png)

Ara editarem l’arxiu ```/etc/nginx/nginx.conf``` i activem la següent linia, això per evitar problemes de memòria quan es treballa amb diversos noms.

![Ara editarem l’arxiu /etc/nginx/nginx.conf i activem la següent linia, això per evitar problemes de memòria quan es treballa amb diversos noms.](Img/Imatge21.png)

```
server_names_hash_bucket_size 64;
```

![Ara editarem l’arxiu /etc/nginx/nginx.conf i activem la següent linia, això per evitar problemes de memòria quan es treballa amb diversos noms.](Img/Imatge22.png)

Verifiquem la sintaxis amb ```nginx -t``` i després d’això reiniciem el servei.

![Verifiquem la sintaxis amb nginx -t i després d’això reiniciem el servei.](Img/Imatge23.png)

Comprovem la IP de l’arxiu ```/etc/hosts``` de la màquina Zorin.

```
sudo nano /etc/hosts
```

![Comprovem la IP de l’arxiu /etc/hosts de la màquina Zorin.](Img/Imatge24.png)

| 3. Personalització d'Errors |
|----------------------------------------|

- **Configureu la directiva error_page 404 dins del bloc de servidor corresponent.**

Configurem la directiva error_page 404 dins del bloc de servidor corresponent.

![- Configureu la directiva error_page 404 dins del bloc de servidor corresponent.
Configurem la directiva error_page 404 dins del bloc de servidor corresponent.](Img/Imatge25.png)

Editem/posem les següents línies per això:

```
server_name www.projectenexus.test;
error_page 404 /404.html
location / {
```

```
}
location = /404.html {
        internal;
}
```

![Editem/posem les següents línies per això:](Img/Imatge26.png)

Reiniciem el servei:

![Reiniciem el servei:](Img/Imatge27.png)

Configurem la directiva error_page 404 dins del bloc de servidor corresponent:

![Configurem la directiva error_page 404 dins del bloc de servidor corresponent:](Img/Imatge28.png)

Editem/posem les següents línies:

```
server_name www.projectenexus.test;
error_page 404 /404.html
location / {
```

```
}
location = /404.html {
        internal;
}
```

![Editem/posem les següents línies](Img/Imatge29.png)

Reiniciem el servei:

![Reiniciem el servei:](Img/Imatge30.png)

- **Assegureu-vos que, quan es demani un fitxer inexistent, es mostri la pàgina d'error personalitzada que vau crear anteriorment.**

Comprovacions:

![- Assegureu-vos que, quan es demani un fitxer inexistent, es mostri la pàgina d'error personalitzada que vau crear anteriorment.
Comprovacions:](Img/Imatge31.png)

![- Assegureu-vos que, quan es demani un fitxer inexistent, es mostri la pàgina d'error personalitzada que vau crear anteriorment.
Comprovacions:](Img/Imatge32.png)

Ara desde la terminal fem una prova de connexió errònia via terminal amb ```curl -L``` i observem com es mostra la redirecció:

![Ara desde la terminal fem una prova de connexió errònia via terminal amb curl -L i observem com es mostra la redirecció:](Img/Imatge33.png)

![Ara desde la terminal fem una prova de connexió errònia via terminal amb curl -L i observem com es mostra la redirecció:](Img/Imatge34.png)

| 4. Seguretat i Certificats (HTTPS) |
|----------------------------------------|

- **Reutilitzeu els certificats SSL generats en l'activitat anterior (o genereu-ne de nous si cal).**

Reutilitzem els certificats SSL generats en l'activitat anterior.

- **Configureu el Server Block per escoltar al port 443 i indiqueu les rutes del certificat (ssl_certificate) i la clau privada (ssl_certificate_key).**

Configurem el Server Block per escoltar al port 443 i indiquem les rutes del certificat (ssl_certificate) i la clau privada (ssl_certificate_key).

Primerament fem un ```cp```:

![- Configureu el Server Block per escoltar al port 443 i indiqueu les rutes del certificat (ssl_certificate) i la clau privada (ssl_certificate_key).
Configurem el Server Block per escoltar al port 443 i indiquem les rutes del certificat (ssl_certificate) i la clau privada (ssl_certificate_key).
Primerament fem un cp:](Img/Imatge35.png)

![- Configureu el Server Block per escoltar al port 443 i indiqueu les rutes del certificat (ssl_certificate) i la clau privada (ssl_certificate_key).
Configurem el Server Block per escoltar al port 443 i indiquem les rutes del certificat (ssl_certificate) i la clau privada (ssl_certificate_key).
Primerament fem un cp:](Img/Imatge36.png)

Entrem a l'arxiu per fer les configuracions corresponents:

![Entrem a l'arxiu per fer les configuracions corresponents:](Img/Imatge37.png)

Posem les següents línies corresponents:

```
server {
        listen 443 ssl;
```

```
server_name www.projectenexus.test;
root /var/www/projectenexus.test;
```

```
ssl_certificate /var/www/projectenexus.test/cert/projectenexus.crt;
ssl_certificate_key /var/www/projectenexus.test/private/projectenexus.key;
ssl_protocols       TLSv1.2 TLSv1.3;
error_page 404 /404.html;
location / {
```

![Posem les següents línies corresponents:](Img/Imatge38.png)

Verifiquem la sintaxis amb ```nginx -t``` i després d’això reiniciem el servei.

![Verifiquem la sintaxis amb nginx -t i després d’això reiniciem el servei.](Img/Imatge39.png)

Habilitarem els sites creant l’enllaç simbòlic cap a la carpeta ```sites-enabled```.

![Habilitarem els sites creant l’enllaç simbòlic cap a la carpeta sites-enabled.](Img/Imatge40.png)

Amb ```ln```, però ja surt.

![Amb ln, però ja surt.](Img/Imatge41.png)

Verifiquem la sintaxis amb ```nginx -t``` i després d’això reiniciem el servei.

![Verifiquem la sintaxis amb nginx -t i després d’això reiniciem el servei.](Img/Imatge42.png)

Ara amb academia el mateix procediment:

![Ara amb academia el mateix procediment:](Img/Imatge43.png)

![Ara amb academia el mateix procediment:](Img/Imatge44.png)

Posem les següents línies corresponents:

```
server {
        listen 443 ssl;
```

```
server_name www.academia.test;
root /var/www/academia.test;
```

```
ssl_certificate /var/www/academia.test/cert/academia.crt;
ssl_certificate_key /var/www/academia.test/private/academia.key;
ssl_protocols       TLSv1.2 TLSv1.3;
error_page 404 /404.html;
location / {
```

![Posem les següents línies corresponents:](Img/Imatge45.png)

![Ara amb academia el mateix procediment:](Img/Imatge46.png)

![Ara amb academia el mateix procediment:](Img/Imatge47.png)

![Ara amb academia el mateix procediment:](Img/Imatge48.png)

- **Redirecció forçada: Configureu un bloc de servidor escoltant al port 80 queretorni un codi 301 (Permanent Redirect) cap a la versió HTTPS del domini projectenexus.test o academia.test.**

Configurem un bloc de servidor escoltant al port 80 que retorni un codi 301 (Permanent Redirect) cap a la versió HTTPS del domini projectenexus.test o academia.test.

Primerament configurem l’arxiu:

![- Redirecció forçada: Configureu un bloc de servidor escoltant al port 80 queretorni un codi 301 (Permanent Redirect) cap a la versió HTTPS del domini projectenexus.test o academia.test.
Configurem un bloc de servidor escoltant al port 80 que retorni un codi 301 (Permanent Redirect) cap a la versió HTTPS del domini projectenexus.test o academia.test.
Primerament configurem l’arxiu:](Img/Imatge49.png)

Posem les següents línies corresponents:

```
server {
        listen 80;
        listen [::]:80;
        server_name www.projectenexus.test;
        return 301 https://www.projectenexus.test$request_uri;
```

```
root /var/www/projectenexus.test;
```

```
error_page 404 /404.html;
location / {
```

```
}
location = /404.html {
        internal;
}
```

![Posem les següents línies corresponents:](Img/Imatge50.png)

Verifiquem la sintaxis amb ```nginx -t``` i després d’això reiniciem el servei.

![Verifiquem la sintaxis amb nginx -t i després d’això reiniciem el servei.](Img/Imatge51.png)

Desde la màquina Zorin fem comprovació amb ```curl -k -I```

![Desde la màquina Zorin fem comprovació amb curl -k -I](Img/Imatge52.png)

Amb academia ja seria el mateix procediment:

![Amb academia ja seria el mateix procediment:](Img/Imatge53.png)

Posem les següents línies corresponents:

```
server {
        listen 80;
        listen [::]:80;
        server_name www.academia.test;
        return 301 https://www.academia.test$request_uri;
```

```
root /var/www/academia.test;
```

```
error_page 404 /404.html;
location / {
```

```
}
location = /404.html {
        internal;
}
```

![Posem les següents línies corresponents:](Img/Imatge54.png)

![Amb academia ja seria el mateix procediment:](Img/Imatge55.png)

![Amb academia ja seria el mateix procediment:](Img/Imatge56.png)

| 5. Optimització amb HTTP/2 |
|----------------------------------------|

- **Habiliteu el protocol HTTP/2 afegint el paràmetre http2 a la directiva listen del bloc SSL.**

- **Comproveu novament amb les eines de desenvolupador del navegador que el contingut s'està servint amb aquest protocol.**

[Anar a l'enunciat](../Tasca03/README.md)  
[Anar a la pàgina inicial](../README.md)

