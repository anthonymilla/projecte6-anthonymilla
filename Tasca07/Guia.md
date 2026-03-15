# TRANSLÒGIC: ADMINISTRACIÓ AVANÇADA I SEGURETAT CORPORATIVA

***Vaig borrar la meva màquina virtual del projecte anterior, aleshores per no començar de 0, vaig exportar la màquina del Pol Hernandez, per si és veu diferent domini i tot això.**

| 1. Polítiques de Seguretat i Contrasenyes (Seguretat Corporativa) |
|----------------------------------------|

- **El client exigeix endurir la política de contrasenyes per evitar accessos no autoritzats:**
- **Política Global: Modifiqueu la Default Domain Policy perquè tots els membres del grup personal (és a dir, tot el domini) hagin de tenir una contrasenya de, com a mínim, 8 caràcters.**           

En Server Manager, en Tools (Eines) anem a Group Policy Management (Gestió de polítiques de grup).   

![- El client exigeix endurir la política de contrasenyes per evitar accessos no autoritzats:
-Política Global: Modifiqueu la Default Domain Policy perquè tots els membres del grup personal (és a dir, tot el domini) hagin de tenir una contrasenya de, com a mínim, 8 caràcters.
En Server Manager, en Tools (Eines) anem a Group Policy Management (Gestió de polítiques de grup).](Img/Imatge01.png)

Seguidament cliquem en Domains (Dominis), translogic13.test, quan es desplega fem clic dret en Default Domain Policy (Política de domini per defecte) i Edit…

![Seguidament cliquem en Domains (Dominis), translogic13.test, quan es desplega fem clic dret en Default Domain Policy (Política de domini per defecte) i Edit…](Img/Imatge02.png)

Ara fem clic en Policies (Polítiques), després en Windows Settings (Configuració del Windows), Security Settings (Configuració de seguretat) i en Account Policies (Polítiques del compte) clic en Password Policy (Política de contrasenyes):

![Ara fem clic en Policies (Polítiques), després en Windows Settings (Configuració del Windows), Security Settings (Configuració de seguretat) i en Account Policies (Polítiques del compte) clic en Password Policy (Política de contrasenyes):](Img/Imatge03.png)

Ara anem a Relax minimum password length limits (Relaxa els límits mínims de longitud de contrasenya) i marquem la casella Define this policy setting (Defineix aquest paràmetre de política) i l’habilitem.

![Ara anem a Relax minimum password length limits (Relaxa els límits mínims de longitud de contrasenya) i marquem la casella Define this policy setting (Defineix aquest paràmetre de política) i l’habilitem.](Img/Imatge04.png)

Ara en Minimum password length (Longitud mínima de la contrasenya) posem 8 characters (caràcters), apliquem i guardem.

![Ara en Minimum password length (Longitud mínima de la contrasenya) posem 8 characters (caràcters), apliquem i guardem.](Img/Imatge05.png)

Resultats:

![Resultats:](Img/Imatge06.png)

- **Política per a Gerència: La Unitat Organitzativa (OU) on ubiqueu la direcció conté els usuaris VIP (grup gerencia). Creeu una GPO específica per ells on la contrasenya sigui de 18 caràcters i caduqui cada 28 dies. No s'ha d'activar la complexitat.**

Anem a Group Policy Management, Domains, després a translogic13.test, baixem el desplegable i anem a Gerencia, clic dret i Create a GPO in this domain, and Link it here… (Crea un GPO en aquest domini, i vincula'l aquí…).

![- Política per a Gerència: La Unitat Organitzativa (OU) on ubiqueu la direcció conté els usuaris VIP (grup gerencia). Creeu una GPO específica per ells on la contrasenya sigui de 18 caràcters i caduqui cada 28 dies. No s'ha d'activar la complexitat.
Anem a Group Policy Management, Domains, després a translogic13.test, baixem el desplegable i anem a Gerencia, clic dret i Create a GPO in this domain, and Link it here… (Crea un GPO en aquest domini, i vincula'l aquí…).](Img/Imatge07.png)

L'anomenarem: Gerencia_

![L'anomenarem: Gerencia_](Img/Imatge08.png)

Creat.

![Creat.](Img/Imatge09.png)

Ara fem clic dret a la GPO creada i Edit.

![Ara fem clic dret a la GPO creada i Edit.](Img/Imatge10.png)

Ara Policies (Polítiques), Windows Settings, baixem el desplegable i en Security Settings anem a Account Policies, Password Policy i clic en Relax minimum password lenght limits (Relaxa els límits mínims de la contrasenya).

![Ara Policies (Polítiques), Windows Settings, baixem el desplegable i en Security Settings anem a Account Policies, Password Policy i clic en Relax minimum password lenght limits (Relaxa els límits mínims de la contrasenya).](Img/Imatge11.png)

L'habilitem.

![L'habilitem.](Img/Imatge12.png)

Seguidament fem clic dret a Minimum password lenght (Contrasenya mínima) i Properties.

![Seguidament fem clic dret a Minimum password lenght (Contrasenya mínima) i Properties.](Img/Imatge13.png)

I posem un mínim de 18 characters (caràcters), apliquem i guardem.

![I posem un mínim de 18 characters (caràcters), apliquem i guardem.](Img/Imatge14.png)

Resultats:

![Resultats:](Img/Imatge15.png)

Ara anem a Maximum password age Properties (Propietats màximes de l'edat de la contrasenya), clic dret a Maximum password age, Properties i posem 28 dies.

![Ara anem a Maximum password age Properties (Propietats màximes de l'edat de la contrasenya), clic dret a Maximum password age, Properties i posem 28 dies.](Img/Imatge16.png)

Si ens fixem surt de Minimum password age 27, l’editem i posem 1 perquè tingui més sentit.

![Si ens fixem surt de Minimum password age 27, l’editem i posem 1 perquè tingui més sentit.](Img/Imatge17.png)

![Si ens fixem surt de Minimum password age 27, l’editem i posem 1 perquè tingui més sentit.](Img/Imatge18.png)

Resultats:

![Resultats:](Img/Imatge19.png)

- **Millora Proactiva (Bonus): Com a consultors experts, heu de proposar i implementar una tercera GPO que considereu útil per a una empresa logística (ex: bloqueig de pantalla automàtic per als usuaris de magatzem per seguretat, fons d'escriptori corporatiu, etc.). Justifiqueu per què l'heu triat.**

| 2. Desplegament Automatitzat de Programari |
|----------------------------------------|

**Per reduir els tiquets de suport tècnic, automatitzareu la instal·lació d'eines segons el departament:**

- **Departament de Gestió: Els administratius (grup gestio) necessiten l'eina de compressió 7zip per gestionar factures. Creeu una GPO per desplegar-la de forma assignada (s'instal·la automàticament).**

El que fem és crear una carpeta anomenada: Software, al nostre disc creat:

![- Departament de Gestió: Els administratius (grup gestio) necessiten l'eina de compressió 7zip per gestionar factures. Creeu una GPO per desplegar-la de forma assignada (s'instal·la automàticament).
El que fem és crear una carpeta anomenada: Software, al nostre disc creat:](Img/Imatge20.png)

![- Departament de Gestió: Els administratius (grup gestio) necessiten l'eina de compressió 7zip per gestionar factures. Creeu una GPO per desplegar-la de forma assignada (s'instal·la automàticament).
El que fem és crear una carpeta anomenada: Software, al nostre disc creat:](Img/Imatge21.png)

Una vegada creada la carpeta, fem clic dret i en Sharing (Compartició) cliquem en Share (Comparteix):

![Una vegada creada la carpeta, fem clic dret i en Sharing (Compartició) cliquem en Share (Comparteix):](Img/Imatge22.png)

Ara en Choose people on your network to share with (Trieu persones a la xarxa amb les quals compartir), escrivim un nom, posarem Everyone (Tothom) i afegim (Add).

![Ara en Choose people on your network to share with (Trieu persones a la xarxa amb les quals compartir), escrivim un nom, posarem Everyone (Tothom) i afegim (Add).](Img/Imatge23.png)

Després Share i Done (Comparteix i Fet).

![Després Share i Done (Comparteix i Fet).](Img/Imatge24.png)

Ara descarregarem 7Zip.

![Ara descarregarem 7Zip.](Img/Imatge25.png)

La quarta opció, el .msi

![La quarta opció, el .msi](Img/Imatge26.png)

Una vegada descarregat el que hem de fer es moure’l a la carpeta anteriorment creada.

![Una vegada descarregat el que hem de fer es moure’l a la carpeta anteriorment creada.](Img/Imatge27.png)

Ara anem al Group Polici Management, Domains, translogic13.test, clic dret i Create a GPO in this domain, and Link it here…

![Ara anem al Group Polici Management, Domains, translogic13.test, clic dret i Create a GPO in this domain, and Link it here…](Img/Imatge28.png)

Posem 7Zip com a nom, OK.

![Posem 7Zip com a nom, OK.](Img/Imatge29.png)

Ara creat, cliquem en aquest i en Security Filtening (Filtenació de seguretat): Add.

![Ara creat, cliquem en aquest i en Security Filtening (Filtenació de seguretat): Add.](Img/Imatge30.png)

I posem el grup: gestio.

![I posem el grup: gestio.](Img/Imatge31.png)

Resultat:

![Resultat:](Img/Imatge32.png)

Podem  treure el Authenticated Users, no fa falta.

![Podem  treure el Authenticated Users, no fa falta.](Img/Imatge322.png)

Ara fem clic dret a la GPO de nou, Edit…

![Ara fem clic dret a la GPO de nou, Edit…](Img/Imatge33.png)

En User Configuration, Policies, Software Settings, clic dret en Software installation, New i Package… (Paquet…):

![En User Configuration, Policies, Software Settings, clic dret en Software installation, New i Package… (Paquet…):](Img/Imatge34.png)

Ara anem al nostre disc i escollim 7zip descarregat.

![Ara anem al nostre disc i escollim 7zip descarregat.](Img/Imatge35.png)

En Deploy Software (Desplega el programari) posem Advanced (Avançat).

![En Deploy Software (Desplega el programari) posem Advanced (Avançat).](Img/Imatge36.png)

Posem en Deployment (Desplegament), en type: Assigned, i en Deployment options (Opcions de desplegament): Install this application at logon (Instal·la aquesta aplicació a l'inici de sessió).

![Posem en Deployment (Desplegament), en type: Assigned, i en Deployment options (Opcions de desplegament): Install this application at logon (Instal·la aquesta aplicació a l'inici de sessió).](Img/Imatge37.png)

Resultat:

![Resultat:](Img/Imatge38.png)

- **Departament de Gerència: Els directius (grup gerencia) necessiten un navegador segur. Creeu una GPO per desplegar Firefox de forma publicada (l'usuari decideix si l'instal·la des del Tauler de Control).**

Primerament descarregarem Firefox.

![- Departament de Gerència: Els directius (grup gerencia) necessiten un navegador segur. Creeu una GPO per desplegar Firefox de forma publicada (l'usuari decideix si l'instal·la des del Tauler de Control).
Primerament descarregarem Firefox.](Img/Imatge39.png)

En MSI Installers (Instal·ladors MSI) fem clic a l'enllaç corresponent:

![En MSI Installers (Instal·ladors MSI) fem clic a l'enllaç corresponent:](Img/Imatge40.png)

Escollim Desktop, Firefox (Recommended).

![Escollim Desktop, Firefox (Recommended).](Img/Imatge41.png)

Windows 64-bit MSI.

![Windows 64-bit MSI.](Img/Imatge42.png)

Idioma:

![Idioma:](Img/Imatge43.png)

Descarreguem.

![Descarreguem.](Img/Imatge44.png)

I ho posem al mateix lloc que el 7Zip, a la carpeta Software.

![I ho posem al mateix lloc que el 7Zip, a la carpeta Software.](Img/Imatge45.png)

En Group Policy Management, en Domains, translogic13.test, baixem el desplegable i la OU Gerencia fem clic dret i Create a GPO in this domain, and Link it here…

![En Group Policy Management, en Domains, translogic13.test, baixem el desplegable i la OU Gerencia fem clic dret i Create a GPO in this domain, and Link it here…](Img/Imatge46.png)

Nom: Firefox.

![Nom: Firefox.](Img/Imatge47.png)

Ara fem clic dret en aquest i Edit.

![Ara fem clic dret en aquest i Edit.](Img/Imatge48.png)

En User Configuration, Policies, Software Settings, clic dret en Software installation, New i Package… (Paquet…):

![En User Configuration, Policies, Software Settings, clic dret en Software installation, New i Package… (Paquet…):](Img/Imatge49.png)

Ara anem al nostre disc i escollim Firefox descarregat.

![Ara anem al nostre disc i escollim Firefox descarregat.](Img/Imatge50.png)

En Deploy Software (Desplega el programari) posem Advanced (Avançat).

![En Deploy Software (Desplega el programari) posem Advanced (Avançat).](Img/Imatge51.png)

Posem en Deployment, en type: Assigned, i en Deployment options: Do not display this package in the Add/Remove Programs control panel (No mostris aquest paquet al panell de control Afegeix/Elimina programes).

![Posem en Deployment, en type: Assigned, i en Deployment options: Do not display this package in the Add/Remove Programs control panel (No mostris aquest paquet al panell de control Afegeix/Elimina programes).](Img/Imatge52.png)

Resultat:

![Resultat:](Img/Imatge53.png)

**Nota tècnica:** Els fitxers .msi els podeu trobar a la carpeta de recursos compartits o descarregar-los. 

| Pregunta de consultoria: |
|----------------------------------------|

**El client us pregunta: "Com podem crear els nostres propis fitxers .msi si una aplicació només ve amb un .exe?". Responeu a l'informe.**

## Resposta:

Si una aplicació només es distribueix en format .exe, podem crear un .msi utilitzant eines de reembalatge (com Advanced Installer o EMCO MSI Package Builder), que converteixen la instal·lació en un paquet .msi apte per desplegar via GPO. Alternativament, si el .exe admet instal·lació silenciosa, es pot desplegar amb scripts. En casos avançats, també és possible doncs generar un .msi manualment amb WiX Toolset.

| 3. Mobilitat d'Usuaris (Perfils Mòbils) |
|----------------------------------------|

**Els usuaris del departament de gestio canvien sovint entre un portàtil o amb un equip d’escriptori.**

- **Habiliteu una carpeta compartida al servidor anomenada perfils.**

- **Configureu la plantilla d'usuari del grup gestio perquè utilitzi un perfil mòbil que es guardi en aquesta carpeta.**

- **Creeu un usuari nou de prova a gestio, inicieu sessió i demostreu que s'ha creat la carpeta del seu perfil al servidor.**

| 4. Seguretat de Dades (Redirecció de Carpetes) |
|----------------------------------------|

**Per evitar pèrdues de dades si un ordinador s'espatlla:**

- **Configureu una directiva per a tot el domini perquè la carpeta local Documents es redirigeixi a una ubicació de xarxa segura (la carpeta home folder que tot usuari té a la xarxa).**

Primerament anem a Group Policy Management, Domains, translogic13.test, clic dret, Create a GPO in this domain, and Link it here… i posem de nom: Redirecció.

![Per evitar pèrdues de dades si un ordinador s'espatlla:
-Configureu una directiva per a tot el domini perquè la carpeta local Documents es redirigeixi a una ubicació de xarxa segura (la carpeta home folder que tot usuari té a la xarxa).
Primerament anem a Group Policy Management, Domains, translogic13.test, clic dret, Create a GPO in this domain, and Link it here… i posem de nom: Redirecció.](Img/Imatge54.png)

Fem clic dret en aquest, Edit… i ara en User Configuration anem a; Policies, Windows Settings, baixem el desplegable, Folder Redirection, Documents, clic dret i Properties.  

![Fem clic dret en aquest, Edit… i ara en User Configuration anem a; Policies, Windows Settings, baixem el desplegable, Folder Redirection, Documents, clic dret i Properties.  ](Img/Imatge55.png)

Ara a Documents Properties, Target (Objectiu), en Setting (Configuració) posem: Basic - Redirect everyone’s folder to the same location (Basic - Redirigeix la carpeta de tothom a la mateixa ubicació), posem en Root Path (Camí d'arrel) la ruta corresponent a la carpeta homes (també podríem posar T05 al davant, per agafar tota la ruta) i Apply i OK.

![Ara a Documents Properties, Target (Objectiu), en Setting (Configuració) posem: Basic - Redirect everyone’s folder to the same location (Basic - Redirigeix la carpeta de tothom a la mateixa ubicació), posem en Root Path (Camí d'arrel) la ruta corresponent a la carpeta homes (també podríem posar T05 al davant, per agafar tota la ruta) i Apply i OK.](Img/Imatge56.png)

Ara anem a la màquina client, entrem amb l’usuari Jan Fernandez, anem a Explorador d’arxius, Documents, clic dret, Propietats, Ubicació, posem la ruta corresponent, apliquem i acceptem:

![Ara anem a la màquina client, entrem amb l’usuari Jan Fernandez, anem a Explorador d’arxius, Documents, clic dret, Propietats, Ubicació, posem la ruta corresponent, apliquem i acceptem:](Img/Imatge57.png)

- **Verifiqueu que, en desar un fitxer a "Documents" des del client, aquest apareix realment al servidor.**

Verifiquem que, en desar un fitxer a "Documents" des del client, aquest apareix realment al servidor. Per això en Documents creem un arxiu de text, per exemple.

![- Verifiqueu que, en desar un fitxer a "Documents" des del client, aquest apareix realment al servidor.
Verifiquem que, en desar un fitxer a "Documents" des del client, aquest apareix realment al servidor. Per això en Documents creem un arxiu de text, per exemple.](Img/Imatge58.png)

Comprovació màquina client i servidor:

![Comprovació màquina client i servidor:](Img/Imatge59.png)

| 5. Delegació de Funcions (Helpdesk) |
|----------------------------------------|

**TransLògic S.A. ha contractat un auxiliar de suport. No volen donar-li les claus de tot el sistema:**

- **Creeu un usuari anomenat adminOU dins la OU d'usuaris.**

Creem un usuari anomenat adminOU dins la OU d'usuaris, per això anem a Active Directory Users and Computers (Usuaris i ordinadors del directori actiu), translogic13.test, baixem el desplegable, Usuaris, New Object - User (Objecte nou - Usuari) i l’anomenem adminOU.

![- Creeu un usuari anomenat adminOU dins la OU d'usuaris.
Creem un usuari anomenat adminOU dins la OU d'usuaris, per això anem a Active Directory Users and Computers (Usuaris i ordinadors del directori actiu), translogic13.test, baixem el desplegable, Usuaris, New Object - User (Objecte nou - Usuari) i l’anomenem adminOU.](Img/Imatge60.png)

Li posem una contrasenya corresponent.

![Li posem una contrasenya corresponent.](Img/Imatge61.png)

Finish.

![Finish.](Img/Imatge62.png)

Resultat:

![Resultat:](Img/Imatge63.png)

- **Delegueu el control de la Unitat Organitzativa principal (ex: OU TransLogic) a aquest usuari adminOU. Només ha de poder:**

Per això en translogic13.test, clic dret i Delegate Control (Delega el control).

![- Delegueu el control de la Unitat Organitzativa principal (ex: OU TransLogic) a aquest usuari adminOU. Només ha de poder:
Per això en translogic13.test, clic dret i Delegate Control (Delega el control).](Img/Imatge64.png)

Ara en Delegation of Control Wizard (Auxiliar de delegació de control); Next.

![Ara en Delegation of Control Wizard (Auxiliar de delegació de control); Next.](Img/Imatge65.png)

Afegim admin OU, Enter the object names to select (Introduïu els noms dels objectes a seleccionar) i OK.

![Afegim admin OU, Enter the object names to select (Introduïu els noms dels objectes a seleccionar) i OK.](Img/Imatge66.png)

Selected users and groups (Usuaris i grups seleccionats), admin OU; Next.

![Selected users and groups (Usuaris i grups seleccionats), admin OU; Next.](Img/Imatge67.png)

- **Reiniciar contrasenyes dels treballadors.**
- **Modificar la pertinença als grups (gestio, magatzem, etc.).**

Ara en Tasks to Delegate (Tasques a delegar), Delegate the following common tasks (Delega les següents tasques comunes) marquem: Reset user passwords and force password change at next logon (Restableix les contrasenyes d'usuari i força el canvi de contrasenya a la següent sessió) i Modify the membership of a group (Modifica la pertinença d'un grup). Next.

![- Reiniciar contrasenyes dels treballadors.
-Modificar la pertinença als grups (gestio, magatzem, etc.).
Ara en Tasks to Delegate (Tasques a delegar), Delegate the following common tasks (Delega les següents tasques comunes) marquem: Reset user passwords and force password change at next logon (Restableix les contrasenyes d'usuari i força el canvi de contrasenya a la següent sessió) i Modify the membership of a group (Modifica la pertinença d'un grup). Next.](Img/Imatge68.png)

Finish.

![Finish.](Img/Imatge69.png)

**Demostreu (amb captures) que l'adminOU pot canviar un password però NO té permisos per crear un usuari nou.**

| Què cal lliurar |
|----------------------------------------|

Informe tècnic:

- Canvis en l’estructura de Unitats Organitzatives i justificar-los.

- Captures de pantalla comentades de cada pas realitzat (GPO creades, configuracions de perfils, logs d'auditoria, etc.).

- Justificació de la 3a GPO: Explicació de quina heu triat i quin benefici aporta a TransLògic.

- Resposta sobre els MSI: Explicació breu de com convertir/crear paquets MSI.

- Proves de funcionament: Captures que demostrin que el client (Windows 10/11) ha aplicat les polítiques (ex: comanda gpresult, carpeta redirigida funcionant, error al intentar crear usuari amb l'adminOU, etc.).

[Anar a l'enunciat](../Tasca07/README.md)  
[Anar a la pàgina inicial](../README.md)
