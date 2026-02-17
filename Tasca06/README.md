# Introducció

Un cop heu resolt el problema de la confidencialitat, Projecte Nexus ha detectat una necessitat crítica: garantir la integritat, autenticitat i el no repudi dels seus documents interns i contractes amb proveïdors. Fins ara signaven en paper, però volen modernitzar-se.

Us han demanat una Prova de Concepte (PoC) per demostrar que podeu muntar una infraestructura pròpia on els seus empleats puguin obtenir certificats digitals corporatius i signar documents PDF oficialment, sense haver de comprar certificats a tercers per a l'ús intern.

# Descripció de l'activitat

Un cop heu resolt el problema de la confidencialitat, Projecte Nexus ha detectat una necessitat crítica: garantir la integritat, autenticitat i el no repudi dels seus documents interns i contractes amb proveïdors. Fins ara signaven en paper, però volen modernitzar-se.

Us han demanat una Prova de Concepte (PoC) per demostrar que podeu muntar una infraestructura pròpia on els seus empleats puguin obtenir certificats digitals corporatius i signar documents PDF oficialment, sense haver de comprar certificats a tercers per a l'ús intern.

## Descripció de l'activitat

L'activitat es divideix en tres fases principals. Treballareu en parelles: un de vosaltres gestionarà el servidor (Administrador de Nexus) i l'altre la màquina client (Treballador de Nexus), col·laborant en tot el procés.

Fase 1: Desplegament de la CA a Windows Server 2025 (Servidor)  
Fase 2: Sol·licitud i Emissió de Certificats via Web (Client)  
Fase 3: Signatura Digital i Verificació (Acrobat Reader)  

## Què cal lliurar

Al repositori del projecte dins la carpeta corresponent a la tasca, heu de lliurar la següent feina:

## Memòria tècnica

- Format Markdown i nom `memoria.md`.  
- Captures de pantalla comentades del procés d'instal·lació del Rol AD CS al Windows Server 2025.  
- Captura del navegador web mostrant el portal `/certsrv`.  
- Captura de la consola del servidor (`certsrv.msc`) mostrant els certificats emesos a nom dels treballadors de Nexus.  
- Captura del `certmgr.msc` del client mostrant el certificat personal instal·lat.  
- Breu explicació de les diferències entre una Clau Pública i una Clau Privada en aquest procés.

## Evidència de la signatura

- El fitxer PDF de prova de Nexus signat digitalment per un dels membres del grup.

## Certificat arrel

- El fitxer .cer de la vostra Autoritat de Certificació (la clau pública de la CA).

# Material de suport

- Material de l’assignatura Seguretat Informàtica. RA3. Signatura electrònica i Certificats Digitals [Moodle de l’assignatura].  
- Guia de l’activitat [enllaç](https://smx2n.github.io/0226-SignaturaElectronica/)

[Anar a la pàgina inicial](../README.md)
