# MP01-Documentacio

## Instalació FOG
Descarreguem FOG desde el link que ens ofereix la pàgina web oficial al nostre servidor Ubuntu,naveguem fins al directori i iniciem l’script installfog.sh. Escrivim 2 per a l'instal·lació Debian basada en Linux:

![Selecció_057](https://github.com/EricQC94/MP01-Documentacio/assets/113598440/c6a755d3-73ba-4639-86dd-320bd0908714)

Configurem les opcions (IP estàtica, màscara, hostname, etc.)

![Selecció_059](https://github.com/EricQC94/MP01-Documentacio/assets/113598440/390bdd9c-2dc6-4fc3-b80f-e14f18692dbf)

Un cop acabats d’emplenar els parametres engeguem una màquina per utilitzar-la de client (Windows) i amb un navegador anem a http://(ip)/fog/management. Després cliquem a Install/Update Now per actualitzar i acabar la instal·lació de FOG:

![Selecció_060](https://github.com/EricQC94/MP01-Documentacio/assets/113598440/037c8d70-c07b-4c18-a213-87dce89227a3)

Ja tenim el Dashboard conforme FOG s’ha instal·lat correctament al servidor:

![Selecció_061](https://github.com/EricQC94/MP01-Documentacio/assets/113598440/b54b645b-4f3a-4a59-bf32-d3f5d8305061)

## Capturar desde el client un Windows

Al FOG management, anem a Images i clickem a Create New Image, aquí només detallem la informació retllevant de la imatge:

![Selecció_074](https://github.com/EricQC94/MP01-Documentacio/assets/113598440/fc9418f8-a5f3-408a-b788-638a643f704e)

Després tanquem client i comencem a instal·lar la màquina Windows que capturarem:

![Selecció_096_install windows](https://github.com/EricQC94/MP01-Documentacio/assets/113598440/1162b2a6-1178-4937-b0a9-bb1492a371ac)

Quan arribem a la sel·lecció de regió apretem Ctrl + Shift + F3 per entrar en Audit Mode (OOBE):

![Selecció_096](https://github.com/EricQC94/MP01-Documentacio/assets/113598440/4826daa9-dc9f-4b0a-bd37-280de6092024)

Windows s’inicia, tanquem finestra de SysPrep:

![Selecció_097](https://github.com/EricQC94/MP01-Documentacio/assets/113598440/e1e722d4-5c41-4c16-a952-14b0d1def305)

Descarreguem ADK:

![Selecció_098](https://github.com/EricQC94/MP01-Documentacio/assets/113598440/6432b411-5740-4a8a-b8f1-0cc7d20efda0)

Instal·lem Deployment Tools:

![Selecció_099](https://github.com/EricQC94/MP01-Documentacio/assets/113598440/424db2eb-8bda-4a32-b119-d33e763f3d8a)

Com es pot observar hem instal·lat Chrome i hem canviat el fons de pantalla a la màquina a capturar:

![Selecció_100](https://github.com/EricQC94/MP01-Documentacio/assets/113598440/5072b9ab-39ae-430c-94f5-ed462df508fa)

Descarreguem FOG Client desde el dashboard de fog (http:/ip/fog/management):

![Selecció_101](https://github.com/EricQC94/MP01-Documentacio/assets/113598440/ed84d79d-ec5d-42e7-85d8-5e35a2a87df1)

Sel·leccionem SmartInstaller:

![Selecció_102](https://github.com/EricQC94/MP01-Documentacio/assets/113598440/f96001a9-41f7-4491-8978-e977a4544d7c)

Instal·lem i fiquem la IP del server:

![Selecció_103](https://github.com/EricQC94/MP01-Documentacio/assets/113598440/b4a9edcf-a633-431f-8198-a7eaece70b5e)

Fiquem ISO de Windows i copiem els fitxers a una carpeta creada a C:, en aquest cas li direm customize/Win10:

![Selecció_104](https://github.com/EricQC94/MP01-Documentacio/assets/113598440/799ed79e-a3bd-41b8-bb39-f3043e418038)


![Selecció_137](https://github.com/EricQC94/MP01-Documentacio/assets/113598440/4174b62a-19bf-4b04-9383-1b51c147de10)

Convertim fitxer install.esd a install.wim amb Powershell:

![Selecció_105](https://github.com/EricQC94/MP01-Documentacio/assets/113598440/4bd974ef-d079-4b6a-a2ad-004f084e4d56)

![Selecció_106](https://github.com/EricQC94/MP01-Documentacio/assets/113598440/dc06c5be-944a-49e4-ba59-512c6e5fa2c4)

Creem un altra carpeta anomenada Distribution amb els següents directoris:

![Selecció_108](https://github.com/EricQC94/MP01-Documentacio/assets/113598440/fac45a32-3d82-4ee9-ba96-8829ef2b8dc4)

Obrim SysPrep i obrim imatge de Windows, després generem fitxer de resposta:

![Selecció_110](https://github.com/EricQC94/MP01-Documentacio/assets/113598440/58b2fadf-e51a-41b9-b228-e0ad932ae9d1)

Validem fitxer de resposta:

![Selecció_111](https://github.com/EricQC94/MP01-Documentacio/assets/113598440/8f8f29f3-ace1-451c-b067-62128cfe6c8e)

El guardem i iniciem Sysprep a una terminal per crear la imatge Generalitzada de Windows 10:

![Selecció_112](https://github.com/EricQC94/MP01-Documentacio/assets/113598440/8a10740a-c0cd-4d77-8908-fec18d1e2be4)

![Selecció_113](https://github.com/EricQC94/MP01-Documentacio/assets/113598440/cfd6078a-6f54-477a-aa75-417de4eacc99)

Anem al Fog dashboard i creem una nova imatge que li direm Win10GeneralImage:

![Selecció_114](https://github.com/EricQC94/MP01-Documentacio/assets/113598440/d1a2694f-1145-4441-b2d6-c0a0509aaa37)

Canviem ordre d’arrencada de la màquina amb Windows 10 per iniciar per xarxa:

![Selecció_115](https://github.com/EricQC94/MP01-Documentacio/assets/113598440/b6b9dc87-c234-4f0a-85d3-c1eca6eb27bf)

Sel·leccionem la següent opció:

![Selecció_116](https://github.com/EricQC94/MP01-Documentacio/assets/113598440/19682a80-c78c-492d-8941-af7ec03d41ef)

Una vegada hem fet el registre tornem al FOG Dashboard, a Hosts per veure si s’ha guardat el registre:

![Selecció_117](https://github.com/EricQC94/MP01-Documentacio/assets/113598440/b0849155-cef7-4068-a1ea-3c60f964d553)

Clickem a sobre i especifiquem la imatge que volem (la que hem creat previament: WIn10GeneralImage):

![Selecció_118](https://github.com/EricQC94/MP01-Documentacio/assets/113598440/2be852a9-65eb-4873-bbbb-0c56e7605eec)

Task management i li donem a  l’icona de capturar:

![Selecció_119](https://github.com/EricQC94/MP01-Documentacio/assets/113598440/6320eb98-195f-44b8-b343-6c95797a4e8f)

Iniciem la màquina de Windows 10 per xarxa i comença la captura:

![Selecció_121](https://github.com/EricQC94/MP01-Documentacio/assets/113598440/77efdcc5-5f55-433e-8f44-d2e4ac78b260)

Ja la tenim capturada:

![Selecció_122](https://github.com/EricQC94/MP01-Documentacio/assets/113598440/f9c16370-1805-4487-9d35-760e43e4d431)

Font: https://www.ceos3c.com/sysadmin/create-generalized-windows-10-image-deploy-fog-server/

## Capturar desde el client un Ubuntu

Primer crearem la màquina de la qual farem la imatge. Hem de tenir en compte que totes les instal·lacions d'aquesta imatge estaran basades en aquesta màquina així que l'hem de configurar i equipar amb apps tenint això en compte.
En el nostre cas també afegirem alguna cosa extra per a que a les captures de pantalla es vegi que la instal·lació per FOG és genuïna

![msg5669090755-5622](https://github.com/EricQC94/MP01-Documentacio/assets/113598440/cfd15a51-2c11-4391-8839-c3f0b165c99c)

Un cop fet això tanquem la màquina i la tornem a engegar posant a l'ordre d'engegada la Xarxa en primer lloc per a connectar-nos al servidor FOG

![msg5669090755-5623](https://github.com/EricQC94/MP01-Documentacio/assets/113598440/379e6bff-41f8-4514-9ec5-7fe242a70bd4)

![msg5669090755-5625](https://github.com/EricQC94/MP01-Documentacio/assets/113598440/d533b72e-73ab-4740-a277-f52c0ddde444)

I posem la ip del servidor.

![msg5669090755-5626](https://github.com/EricQC94/MP01-Documentacio/assets/113598440/9fed0a7a-1dfd-4569-9882-c4055846889b)

Ara seleccionem la opció de "Perform Full Host Registration and Inventory" per a que la imatge quedi capturada al servidor FOG.

![msg5669090755-5627](https://github.com/EricQC94/MP01-Documentacio/assets/113598440/a9ff6561-b40b-4f36-bd1c-a7a4316408f4)

![msg5669090755-5628](https://github.com/EricQC94/MP01-Documentacio/assets/113598440/1524f439-712e-468e-8212-b0455f0d2d4d)

![msg5669090755-5629](https://github.com/EricQC94/MP01-Documentacio/assets/113598440/5bf58b7a-24df-471f-b692-09adddb3c0fb)

![msg5669090755-5630](https://github.com/EricQC94/MP01-Documentacio/assets/113598440/78e6f9b9-4edc-416b-b621-6c22c127c679)

![msg5669090755-5631](https://github.com/EricQC94/MP01-Documentacio/assets/113598440/bdb3a32b-b89a-4188-859f-d14ef97c06a5)

![msg5669090755-5632](https://github.com/EricQC94/MP01-Documentacio/assets/113598440/58318026-cc9f-4937-814f-f90643b1a613)

![msg5669090755-5634](https://github.com/EricQC94/MP01-Documentacio/assets/113598440/3c3526f2-a3d8-4ee0-ad53-b5d8a9a0bcc6)


Ara hauria d'estar preparada per a instal·lar a altres màquines.

# Instal·lar imatge Ubuntu

Un cop capturada la imatge només hem de crear una nova màquina virtual d'ubuntu. En aquest cas no posarem cap imatge amb la que instal·lar el SO ja que aquest vindra del servidor FOG. Per tant a paràmetres tornem a posar la Xarxa al principi del "boot":

![msg5669090755-5623](https://github.com/EricQC94/MP01-Documentacio/assets/113598440/f18ca597-af24-4c7e-9dac-aadc1d6b0834)


Llavors fem el "login" al servidor:

![msg5669090755-5637](https://github.com/EricQC94/MP01-Documentacio/assets/113598440/1299eea2-19b4-409a-9a44-181eaa159e41)


Triem la opció de "Deploy" al menú i elegim la imatge que necessitem:

![msg5669090755-5638](https://github.com/EricQC94/MP01-Documentacio/assets/113598440/eaae07a6-073a-4727-94df-cbb3b841dba3)


I la instal·lació començarà:

![msg5669090755-5639](https://github.com/EricQC94/MP01-Documentacio/assets/113598440/d93af9e3-ac33-445a-bc02-8738ec56a17f)


Un cop acabada tornem als paràmetres de la màquina, desactivem Xarxa del "boot sequence" i la tornem a engegar per a comprovar que la instal·lació ha estat un èxit:

![msg5669090755-5640](https://github.com/EricQC94/MP01-Documentacio/assets/113598440/9cef523d-4647-47f2-9838-95c8f6601b36)


## Instalar imatge Windows

Creem una màquina de 0 sense ISO, fiquem xarxa NAT igual que el servidor Fog:

![Selecció_130](https://github.com/EricQC94/MP01-Documentacio/assets/113598440/7cdd3548-4d74-47ba-b0ef-f120736061af)

![Selecció_131](https://github.com/EricQC94/MP01-Documentacio/assets/113598440/cfee3a29-2e07-4d5f-815b-cc234975b400)

Entrem al FOG i fiquem Deploy Image:

![Selecció_133](https://github.com/EricQC94/MP01-Documentacio/assets/113598440/2a7ce316-17ee-469d-920e-337b6e840e4f)

Sel·leccionem la imatge de Windows:

![Selecció_132](https://github.com/EricQC94/MP01-Documentacio/assets/113598440/36648fdf-449a-468e-b3e5-496897967084)

Comença a planxar-se:

![Selecció_134](https://github.com/EricQC94/MP01-Documentacio/assets/113598440/1f4e7cd1-7dd1-43b3-aa60-a81c15a44b5d)

No s’ha guardat el fons de pantalla, però Chrome està instal·lat:

![Selecció_136](https://github.com/EricQC94/MP01-Documentacio/assets/113598440/3a34bda7-9749-4502-81d3-8491a6c09299)














