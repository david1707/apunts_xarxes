![[model_osi.png]]

## Capa 7: Aplicació

Proveeix d'accés a usuaris.

En aquesta capa no estan les aplicacions en sí, si no aplicacions bàsiques com Telnet, HTTP, FTP, etc.

## Capa 6: Presentació

El format de com la informació és representada. Fa que la informació siga llegible pel sistema que la rep (és a dir, és llegible). Pot proveir encriptació.

JPEG, BMP, Mp3, ASCII, zip, etc.

## Capa 5: Sessió

Aquesta capa s'encarrega de la connexió entre dispositius (Comunicació interhost). Fa l'establiment, manteniment i tancament de sessions entre aplicacions. Dues aplicacions en diferents màquines poden crear una sessió.

NetBIOS, API, Sockets....

## Capa 4: Transport

Gestiona les comunicacions i el seu control entre hosts i sistemes per assegurar-se que la informació és correctament transportada.

TCP i UDP

## Capa 3: Network (Xarxa) layer

Dedicada a l'enviament de paquets d'informació, mitjançant routers, d'un sistema a un altre. Switches de nivell 3 també tenen aquesta capacitat. Poden utilitzar el **OSPF** (Open Shortest Path First) o **BGP** (Border Gateway Protocol)

Routers, Switches.

## Capa 2: Data-link

Permet la transferència d'informació entre els nodes de les capes 3 (Network) i 1 (Físic). Defineix com la informació és formatada i com l'accés a la xarxa és controlada.

Ethernet.

## Capa 1: Física

Defineix com la informació és transmesa (binària). Defineix les especificacions elèctriques, mecàniques, procedural i funcional per controlar els dispositius d'aquesta capa. Tot i transmetre tots dos informació, els cables de coure i fibra, per exemple, tenen diferents especificacions.

