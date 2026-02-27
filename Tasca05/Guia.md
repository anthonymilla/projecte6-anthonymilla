# TOP SECRET, PROTEGINT ELS SECRETS

## Introducció

Aprofitant que ja hi esteu treballant amb la seva infraestructura web, des de Projecte Nexus us sol·licita una nova petició d’ajuda.          
A causa del gran volum de dades sensibles que gestionen (dades personals d'estudiants, exàmens oficials no publicats i certificats de notes), estan molt preocupats per la integritat i privacitat de la seva gestió acadèmica.    
La direcció de Projecte Nexus us ha demanat una demostració pràctica de com la vostra empresa pot garantir els tres pilars de la seguretat en la seva informació: **Confidencialitat, Integritat i Autenticitat.**

**Descripció de l'activitat**

| Tasca 1: Protecció de dades en repòs (Xifratge Simètric) |
|----------------------------------------|

Els caps de departament necessiten transportar els exàmens finals en memòries USB per imprimir-los a secretaria, però tenen por de perdre el dispositiu i que les preguntes es filtrin abans de la data de la prova.

Heu de crear un contenidor xifrat (unitat virtual) dins d'un pendrive (simulat al disc dur) utilitzant el programari VeraCrypt (o similar).

Instal·lem VeraCrypt.

![Heu de crear un contenidor xifrat (unitat virtual) dins d'un pendrive (simulat al disc dur) utilitzant el programari VeraCrypt (o similar).
Instal·lem VeraCrypt.](Img/Imatge01.png)

![Heu de crear un contenidor xifrat (unitat virtual) dins d'un pendrive (simulat al disc dur) utilitzant el programari VeraCrypt (o similar).
Instal·lem VeraCrypt.](Img/Imatge02.png)

**Requisits:**

- Crear un volum de 100MB.             
Després de crear la màquina en adaptador pont, pausar les actualitzacions, ja podem començar. Primerament, posem la xarxa en: Xarxa NAT i creem el volum de 100 MB      
(Vaig haver de fer el volum varies vegades de nou, ja que no ho feia bé i havia de tornar-ho a fer. Per això, per si es veiessin diferents opcions, moments, moltes captures…).

![- Crear un volum de 100MB.             
Després de crear la màquina en adaptador pont, pausar les actualitzacions, ja podem començar. Primerament, posem la xarxa en: Xarxa NAT i creem el volum de 100 MB.
(Vaig haver de fer el volum varies vegades de nou, ja que no ho feia bé i havia de tornar-ho a fer. Per això, per si es veiessin diferents opcions, moments, moltes captures…)](Img/Imatge03.png)

Anem a Paràmetres, Emmagatzematge i crear disc.

![Anem a Paràmetres, Emmagatzematge i crear disc.](Img/Imatge04.png)

Creat, cliquem d'acord i iniciem la màquina.

![Creat, cliquem d'acord i iniciem la màquina.](Img/Imatge05.png)

Dins de la màquina, anem a Administració de discos i Inicialitzem el disc (GPT).

![Dins de la màquina, anem a Administració de discos i Inicialitzem el disc (GPT).](Img/Imatge06.png)

Després com veiem, està inicialitzat.

![Després com veiem, està inicialitzat.](Img/Imatge07.png)

Ara l’assignem, per això fem clic dret sobre el disc, anem a Nou volum simple (Podríem posar de nom: Pen, perquè tingui una millor referència, però no he posat nom directament, però perquè s’entengui) i acceptem.

![Ara l’assignem, per això fem clic dret sobre el disc, anem a Nou volum simple (Podríem posar de nom: Pen, perquè tingui una millor referència, però no he posat nom directament, però perquè s’entengui) i acceptem.](Img/Imatge08.png)

Ja estaria.

![Ja estaria.](Img/Imatge09.png)

- Utilitzar l'algorisme de xifratge AES-256.        
Ara anem a l'aplicació de VeraCrypt i cliquem en “Crear Volum”.

![- Utilitzar l'algorisme de xifratge AES-256.        
Ara anem a l'aplicació de VeraCrypt i cliquem en “Crear Volum”.](Img/Imatge10.png)

Primerament posem l'opció de xifrar partició/unitat secundaria. Següent.

![Primerament posem l'opció de xifrar partició/unitat secundaria. Següent.](Img/Imatge11.png)

Ara en tipus de volum posem: Volum VeraCrypt comú.

![Ara en tipus de volum posem: Volum VeraCrypt comú.](Img/Imatge12.png)

Després a ubicació del volum, anem a seleccionar dispositiu.

![Després a ubicació del volum, anem a seleccionar dispositiu.](Img/Imatge13.png)

I escollim el disc creat.

![I escollim el disc creat.](Img/Imatge14.png)

Escollit. Següent.

![Escollit. Següent.](Img/Imatge15.png)

En mode de creació de volum, xifrem la partició conservant dades.

![En mode de creació de volum, xifrem la partició conservant dades.](Img/Imatge16.png)

- Utilitzar l'algorisme de xifratge AES-256.    
Utilitzem l'algorisme de xifratge AES i l’algorisme hash SHA-256. Següent.

![- Utilitzar l'algorisme de xifratge AES-256.    
Utilitzem l'algorisme de xifratge AES i l’algorisme hash SHA-256. Següent.](Img/Imatge17.png)

- Establir una contrasenya robusta.      
Contrasenya robusta: T$9mZ!4qP@82rF#xL1

![- Establir una contrasenya robusta.      
Contrasenya robusta: T$9mZ!4qP@82rF#xL1](Img/Imatge18.png)

Ara recopila dades aleatòries, nosaltres en aquest apartat el que hem de fer és moure el ratolí per la pantalla fins que la barra estigui al complet en verd i continuem.

![Ara recopila dades aleatòries, nosaltres en aquest apartat el que hem de fer és moure el ratolí per la pantalla fins que la barra estigui al compet en verd i continuem.](Img/Imatge19.png)

En el mode esborrat, ho deixem com està predeterminat, continuem.

![En el mode esborrat, ho deixem com està predeterminat, continuem.](Img/Imatge20.png)

Seguidament xifrem, cliquem on posa: Xifrar.

![Seguidament xifrem, cliquem on posa: Xifrar.](Img/Imatge21.png)

I el volum ja estaria xifrat. Finalitzem.

![I el volum ja estaria xifrat. Finalitzem.](Img/Imatge22.png)

Ara seleccionem dispositiu.

![Ara seleccionem dispositiu.](Img/Imatge23.png)

I l’escollim.

![I l’escollim. ](Img/Imatge24.png)

Després escollim una lletra i muntem.

![Després escollim una lletra i muntem.](Img/Imatge25.png)

Posem la contrasenya robusta que hem establert anteriorment.

![Posem la contrasenya robusta que hem establert anteriorment.](Img/Imatge26.png)

I ja estaria muntat.

![I ja estaria muntat.](Img/Imatge27.png)

Comprovem com s’ha muntat correctament, és accessible, es veu.

![Comprovem com s’ha muntat correctament, és accessible, es veu.](Img/Imatge28.png)

- Dins la unitat xifrada, heu de copiar un fitxer de text anomenat EXAMEN_FINAL_SEGURETAT.txt amb preguntes de prova.      
Primerament, creo el fitxer de text anomenat EXAMEN_FINAL_SEGURETAT.txt amb alguna pregunta de prova.

![- Dins la unitat xifrada, heu de copiar un fitxer de text anomenat EXAMEN_FINAL_SEGURETAT.txt amb preguntes de prova.      
Primerament, creo el fitxer de text anomenat EXAMEN_FINAL_SEGURETAT.txt amb alguna pregunta de prova.](Img/Imatge29.png)

I copiem el fitxer de text anomenat EXAMEN_FINAL_SEGURETAT.txt a la unitat xifrada.

![I copiem el fitxer de text anomenat EXAMEN_FINAL_SEGURETAT.txt a la unitat xifrada.](Img/Imatge30.png)

- Demostrar que, sense muntar la unitat amb la contrasenya, el fitxer és inaccessible.       
Ara el que hem de fer és desmuntar. Anem a VeraCrypt i cliquem en: Desmuntar.

![- Demostrar que, sense muntar la unitat amb la contrasenya, el fitxer és inaccessible.       
Ara el que hem de fer és desmuntar. Anem a VeraCrypt i cliquem en: Desmuntar.](Img/Imatge31.png)

Veiem que s’ha desmuntat correctament.

![Veiem que s’ha desmuntat correctament.](Img/Imatge32.png)

Fem la comprovació, i podem veure com sense muntar la unitat amb la contrasenya, el fitxer és inaccessible.

![Fem la comprovació, i podem veure com sense muntar la unitat amb la contrasenya, el fitxer és inaccessible.](Img/Imatge33.png)

| Tasca 2: Verificació d'Integritat (Hashing) |
|----------------------------------------|

Nexus distribueix material didàctic i software als alumnes a través del seu servidor web.          
Volen estar segurs que els fitxers no han estat alterats per un atacant per incloure malware.

- Utilitzant una eina com CertUtil (Windows), md5sum/sha256sum (Linux) o 7-Zip:     
Utilitzem l’eina CertUtil, anem a la terminal i posem la comanda certutil si ens surt comando completado correctamente vol dir que funciona (prova de que funciona):

![- Utilitzant una eina com CertUtil (Windows), md5sum/sha256sum (Linux) o 7-Zip:     
Utilitzem l’eina CertUtil, anem a la terminal i posem la comanda certutil si ens surt comando completado correctamente vol dir que funciona (prova de que funciona):](Img/Imatge34.png)

- Crear un document de text anomenat nota_final_curs.txt amb el text: "L'alumne ha aprovat amb un 5".       
Creem un document de text anomenat nota_final_curs.txt amb el text: "L'alumne ha aprovat amb un 5".

![- Crear un document de text anomenat nota_final_curs.txt amb el text: "L'alumne ha aprovat amb un 5".       
Creem un document de text anomenat nota_final_curs.txt amb el text: "L'alumne ha aprovat amb un 5".](Img/Imatge35.png)

![- Crear un document de text anomenat nota_final_curs.txt amb el text: "L'alumne ha aprovat amb un 5".       
Creem un document de text anomenat nota_final_curs.txt amb el text: "L'alumne ha aprovat amb un 5".](Img/Imatge36.png)

Creem una carpeta anomenada “Xifrat” en aquest cas i posem el document de text a dins. Creat correctament:

![Creem una carpeta anomenada “Xifrat” en aquest cas i posem el document de text a dins. Creat correctament:](Img/Imatge37.png)

- Calcular el Hash SHA-256 del fitxer original.       
Ara calcularem el Hash SHA-256 del fitxer, per això copiem la ruta:

![- Calcular el Hash SHA-256 del fitxer original.       
Ara calcularem el Hash SHA-256 del fitxer, per això copiem la ruta:](Img/Imatge38.png)

I anem a terminal, on posem la següent comanda copiant la ruta i ens calcula el Hash SHA-256 del fitxer:

![I anem a terminal, on posem la següent comanda copiant la ruta i ens calcula el Hash SHA-256 del fitxer:](Img/Imatge39.png)

- Modificar el fitxer canviant una sola xifra (ex: "L'alumne ha aprovat amb un 9").      
Ara modifiquem el fitxer, canviem el 5 per el 9.

![- Modificar el fitxer canviant una sola xifra (ex: "L'alumne ha aprovat amb un 9").      
Ara modifiquem el fitxer, canviem el 5 per el 9.](Img/Imatge40.png)

- Tornar a calcular el Hash i comparar els resultats per demostrar com l'empremta digital canvia totalment i revela la manipulació de la nota.        
Ara tornem a fer la comanda i com podem veure com l'empremta digital canvia totalment i revela la manipulació de la nota.

![- Tornar a calcular el Hash i comparar els resultats per demostrar com l'empremta digital canvia totalment i revela la manipulació de la nota.        
Ara tornem a fer la comanda i com podem veure com l'empremta digital canvia totalment i revela la manipulació de la nota.](Img/Imatge41.png)

| Justificació Teòrica de la diferència entre xifratge i funció hash: |
|----------------------------------------|
El xifratge serveix per amagar la informació perquè ningú la pugui llegir si no té la contrasenya. És reversible ja que si tens la clau, pots recuperar el fitxer original.
La funció hash, en canvi, no amaga res, sinó que crea una mena d’“empremta digital” del fitxer. Aquesta empremta no es pot revertir i serveix per comprovar que el document no ha estat modificat. 
Bàsicament el xifratge és protegir i ocultar dades i el hash és assegurar que no s’han canviat.

| Conclusió: |
|----------------------------------------|

Doncs què és important que Nexus xifri totes les dades sensibles, sobretot les que es porten en USB o discos externs, per evitar que algú les pugui llegir si es perden o són robades. També doncs cal usar contrasenyes fortes i guardar-les de manera segura. També és recomanable utilitzar funcions hash per comprovar la integritat de documents importants (com notes, contractes…), així assegurant que ningú els ha modificat sense permís.

| Què cal lliurar |
|----------------------------------------|

Heu de redactar un informe tècnic per al client (format MarkDown) que inclogui:

**Justificació Teòrica:** Una breu explicació (màxim 10 línies) per al client de la diferència
entre xifratge (Tasca 1) i funció hash (Tasca 2), explicant que el xifratge amaga la informació i el hash en garanteix la integritat.

**Evidències de la Tasca 1:**

- Captura de pantalla de la configuració del volum (algorisme escollit).
- Captura de la unitat muntada amb l'examen secret a dins.
- Captures que permetin veure el procés per accedir al fitxer.

**Evidències de la Tasca 2 (Hashing):**

Captura de pantalla del terminal o programa mostrant els dos hashos (l'original i el modificat) per veure que són diferents.

**Conclusió:** Breu recomanació final a Nexus sobre la importància de protegir les dades , especialment les portables amb xifrat i la gestió segura de les contrasenyes (robustesa i com guardar-les). A continuació, la necessitat d’usar hash per assegurar la integritat de la documentació important com actes de notes, contractes, etc.

[Anar a l'enunciat](../Tasca02/README.md)  
[Anar a la pàgina inicial](../README.md)
