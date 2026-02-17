# Introducció

Malgrat que l’encàrrec de Projecte Nexus consumeix bona part de la vostra energia i temps, no podeu deixar de banda els clients existents. TransLògic S.A. va confiar amb vosaltres per fer el salt a una infraestructura amb Directori Actiu, i ara, cal rematar el projecte.  

Cal realitzar una sèrie de millores crítiques en la seva infraestructura de xarxa. La direcció de l'empresa està preocupada per la seguretat de les contrasenyes, la mobilitat dels seus treballadors i la gestió eficient del programari. A més, volen començar a delegar certes tasques bàsiques a un assistent tècnic sense donar-li privilegis totals d'administrador.

# Descripció de l'activitat

Heu de documentar cada pas com si fos un informe tècnic d'implementació per al client. Abans de començar a realitzar les diferents accions, repenseu l’estructura d’unitats organitzatives (OU) que vau presentar inicialment al client, és possible que algun canvi us simplifiqui les accions que caldrà realitzar.

1. Polítiques de Seguretat i Contrasenyes (Seguretat Corporativa)

- El client exigeix endurir la política de contrasenyes per evitar accessos no autoritzats:
- Política Global: Modifiqueu la Default Domain Policy perquè tots els membres del grup personal (és a dir, tot el domini) hagin de tenir una contrasenya de, com a mínim, 8 caràcters.  
- Política per a Gerència: La Unitat Organitzativa (OU) on ubiqueu la direcció conté els usuaris VIP (grup gerencia). Creeu una GPO específica per ells on la contrasenya sigui de 18 caràcters i caduqui cada 28 dies. No s'ha d'activar la complexitat.  
- Millora Proactiva (Bonus): Com a consultors experts, heu de proposar i implementar una tercera GPO que considereu útil per a una empresa logística (ex: bloqueig de pantalla automàtic per als usuaris de magatzem per seguretat, fons d'escriptori corporatiu, etc.). Justifiqueu per què l'heu triat.

2. Desplegament Automatitzat de Programari

Per reduir els tiquets de suport tècnic, automatitzareu la instal·lació d'eines segons el departament:

- Departament de Gestió: Els administratius (grup gestio) necessiten l'eina de compressió 7zip per gestionar factures. Creeu una GPO per desplegar-la de forma assignada (s'instal·la automàticament).  
- Departament de Gerència: Els directius (grup gerencia) necessiten un navegador segur. Creeu una GPO per desplegar Firefox de forma publicada (l'usuari decideix si l'instal·la des del Tauler de Control).  

**Nota tècnica:** Els fitxers .msi els podeu trobar a la carpeta de recursos compartits o descarregar-los.  
**Pregunta de consultoria:** El client us pregunta: "Com podem crear els nostres propis fitxers .msi si una aplicació només ve amb un .exe?". Responeu a l'informe.

3. Mobilitat d'Usuaris (Perfils Mòbils)

Els usuaris del departament de gestio canvien sovint entre un portàtil o amb un equip d’escriptori.

- Habiliteu una carpeta compartida al servidor anomenada `perfils`.  
- Configureu la plantilla d'usuari del grup gestio perquè utilitzi un perfil mòbil que es guardi en aquesta carpeta.  
- Creeu un usuari nou de prova a gestio, inicieu sessió i demostreu que s'ha creat la carpeta del seu perfil al servidor.

4. Seguretat de Dades (Redirecció de Carpetes)

Per evitar pèrdues de dades si un ordinador s'espatlla:

- Configureu una directiva per a tot el domini perquè la carpeta local `Documents` es redirigeixi a una ubicació de xarxa segura (la carpeta home folder que tot usuari té a la xarxa).  
- Verifiqueu que, en desar un fitxer a "Documents" des del client, aquest apareix realment al servidor.

5. Delegació de Funcions (Helpdesk)

TransLògic S.A. ha contractat un auxiliar de suport. No volen donar-li les claus de tot el sistema:

- Creeu un usuari anomenat `adminOU` dins la OU d'usuaris.  
- Delegueu el control de la Unitat Organitzativa principal (ex: OU TransLogic) a aquest usuari `adminOU`. Només ha de poder: 
  - Reiniciar contrasenyes dels treballadors.  
  - Modificar la pertinença als grups (gestio, magatzem, etc.).  

Demostreu (amb captures) que l'adminOU pot canviar un password però NO té permisos per crear un usuari nou.

# Què cal lliurar

Informe tècnic:

  - Canvis en l’estructura de Unitats Organitzatives i justificar-los.  
  - Captures de pantalla comentades de cada pas realitzat (GPO creades, configuracions de perfils, logs d'auditoria, etc.).  
  - Justificació de la 3a GPO: Explicació de quina heu triat i quin benefici aporta a TransLògic.  
  - Resposta sobre els MSI: Explicació breu de com convertir/crear paquets MSI.  
  - Proves de funcionament: Captures que demostrin que el client (Windows 10/11) ha aplicat les polítiques (ex: comanda gpresult, carpeta redirigida funcionant, error al intentar crear usuari amb l'adminOU, etc.).

