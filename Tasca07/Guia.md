# TRANSLÒGIC: ADMINISTRACIÓ AVANÇADA I SEGURETAT CORPORATIVA

***Vaig borrar la meva màquina virtual del projecte anterior, aleshores per no començar de 0, vaig exportar la màquina del Pol Hernandez, per si és veu diferent domini i tot això.**

| 1. Polítiques de Seguretat i Contrasenyes (Seguretat Corporativa) |
|----------------------------------------|

- El client exigeix endurir la política de contrasenyes per evitar accessos no autoritzats:
- Política Global: Modifiqueu la Default Domain Policy perquè tots els membres del grup personal (és a dir, tot el domini) hagin de tenir una contrasenya de, com a mínim, 8 caràcters.           

En Server Manager, en Tools (Eines) anem a Group Policy Management (Gestió de polítiques de grup).   

![- El client exigeix endurir la política de contrasenyes per evitar accessos no autoritzats:
-Política Global: Modifiqueu la Default Domain Policy perquè tots els membres del grup personal (és a dir, tot el domini) hagin de tenir una contrasenya de, com a mínim, 8 caràcters.
En Server Manager, en Tools (Eines) anem a Group Policy Management (Gestió de polítiques de grup).](Img/Imatge01.png)

Seguidament cliquem en Domains (Dominis), translogic13.test, quan es desplega fem clic dret en Default Domain Policy (Política de domini per defecte) i Edit…

![Seguidament cliquem en Domains (Dominis), translogic13.test, quan es desplega fem clic dret en Default Domain Policy (Política de domini per defecte) i Edit…](Img/Imatge02.png)

Ara fem clic en Policies (Polítiques), després en Windows Settings (Configuració del Windows), Security Settings (Configuració de seguretat) i en Account Policies (Polítiques del compte) clic en Password Policy (Política de contrasenyes):

![Ara fem clic en Policies (Polítiques), després en Windows Settings (Configuració del Windows), Security Settings (Configuració de seguretat) i en Account Policies (Polítiques del compte) clic en Password Policy (Política de contrasenyes):](Img/Imatge03.png)

Ara anem a Relax minimum password length limits (Relaxa els límits mínims de longitud de contrasenya) i marquem la casella Define the policy setting (Defineix la configuració de la política) i l’habilitem.

![Ara anem a Relax minimum password length limits (Relaxa els límits mínims de longitud de contrasenya) i marquem la casella Define the policy setting (Defineix la configuració de la política) i l’habilitem.](Img/Imatge04.png)

Ara en Minimum password length (Longitud mínima de la contrasenya) posem 8 characters.

![Ara en Minimum password length (Longitud mínima de la contrasenya) posem 8 characters.](Img/Imatge05.png)

Resultats:

![Resultats:](Img/Imatge06.png)

- Política per a Gerència: La Unitat Organitzativa (OU) on ubiqueu la direcció conté els usuaris VIP (grup gerencia). Creeu una GPO específica per ells on la contrasenya sigui de 18 caràcters i caduqui cada 28 dies. No s'ha d'activar la complexitat.

Anem a Tools i Active Directory Users and Computers (Usuaris i ordinadors del directori actiu).

![- Política per a Gerència: La Unitat Organitzativa (OU) on ubiqueu la direcció conté els usuaris VIP (grup gerencia). Creeu una GPO específica per ells on la contrasenya sigui de 18 caràcters i caduqui cada 28 dies. No s'ha d'activar la complexitat.
Anem a Tools i Active Directory Users and Computers (Usuaris i ordinadors del directori actiu).](Img/Imatge07.png)



![Creem una nova OU anomenada Gerència.](Img/Imatge08.png)



![Afegim grup i un usuari dins.](Img/Imatge09.png)



![Ara, tornem a Group Policy Management, en Domains anem a translogic13.test, fem clic dret i Create a GPO in this domain, and Link it here… (Crea un GPO en aquest domini, i enllaça'l aquí…)](Img/Imatge10.png)



![Nom:](Img/Imatge11.png)



![Resultat, Linked Group Policy Objects (Objectes de política de grup enllaçats).](Img/Imatge12.png)



![Anem a la GPO i Edit…](Img/Imatge13.png)



![En Preferences, Drive Maps (Controla els mapes), clic dret, New i Mappet Drive (Unitat de Mappet).](Img/Imatge14.png)



![I configurem corresponentment el New Drive Properties (Propietats de la unitat nova).](Img/Imatge15.png)



![Resultat:](Img/Imatge16.png)

![Comprovacions.](Img/Imatge17.png)

![Comprovacions.](Img/Imatge18.png)

![Comprovacions.](Img/Imatge19.png)

![Comprovacions.](Img/Imatge20.png)

![Comprovacions.](Img/Imatge21.png)

![Comprovacions.](Img/Imatge22.png)

![Comprovacions.](Img/Imatge23.png)

![Comprovacions.](Img/Imatge24.png)

![Comprovacions.](Img/Imatge25.png)

![Comprovacions.](Img/Imatge26.png)

![Comprovacions.](Img/Imatge27.png)

![Comprovacions.](Img/Imatge28.png)

![Comprovacions.](Img/Imatge29.png)

![Comprovacions.](Img/Imatge30.png)

![Comprovacions.](Img/Imatge31.png)

[Anar a l'enunciat](../Tasca07/README.md)  
[Anar a la pàgina inicial](../README.md)
