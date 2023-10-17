
## Desencapsulació

Procés invers de la [[#Encapsulació]].

## DHCP o Dynamic Host Configuration Protocol

Protocol que proporciona dinàmicament (automàticament) una adreça IP i la configuració necessària per a que aquesta funcione.

## DNS o Domain Name System

El sistema pel qual una URL (www.google.com) es tradueix a una adreça IP (8.8.8.8) que els dispositius encarregats de les connexions poden entendre i, pel tant, enrutar la informació a través d'internet.

## Encapsulació

El procés en el qual a la informació se li van afegint headers de cada capa del model OSI, contenint meta-informació sobre aquestes. [[Model OSI - General#Comunicació entre dispositius|Més informació]]

## IP Address (Adreça IP)

Direcció numèrica assignada a cada dispositiu que participa en una xarxa. És l'equivalent a una adreça d'una casa.

## Model OSI

Standard basat [[Model OSI - General|en capes]] creat per la Organització Internacional per la Estandardització (OSI), que permet communicar-se seguint un standard a diferents dispositius i sistemes de comunicació, sense la necessitat d'entendre els protocols.

## Network Interface Card (Targeta de xarxa)

Connecta un dispositiu (PC, portàtil) a una xarxa (Local, Internet, etc).

![[NIC.png]]

## Network Protocol (Protocol de xarxa)

Conjunt de regles i convencions que indiquen com han de ser les comunicacions entre dispositius en una xarxa.

Dos (o més) dispositius han d'entendre's entre ells, de la mateixa que dos o més persones s'han d'entendre parlant un mateix idioma. Aquest "idioma" el marca aquest protocol.

## Ping

Eina que ens serveix per comprovar si tenim connectivitat a un lloc o xarxa remota, o una pàgina web.

```
ping <IP/URL>

ping 8.8.8.8
ping google.com
```

![[ping.png]]

## SOHO Network (Oficina petita o de casa: Small Office/Home Office)

Xarxa d'un negoci on treballen entre 1 i 10 treballadors.

![[SOHO.png]]

## Tipus de xarxes

### PAN (Personal Area Network)

Xarxes petites utilitzades per ús personal per compartir informació d'un dispositiu a altre (de mòbil a portàtil, de smart watch a mòbil...).

### LAN (Local Area Network)

És una xarxa d'una zona relativament xicoteta, com una habitació, casa, edifici o grup d'edificis. (Una xarxa de casa o d'una oficina).

### WLAN (Wireless Local Area Network)

Similar a una LAN, però amb connectivitat sense fils (WIFI). La més habitual.

### WAN (Wide Area Network)

Una xarxa que abasta molta distància, entre multiples ciutats o, fins i tot, països (Internet, Google Offices en diferents països, etc).

## Topologia

La topologia d'una xarxa és l'estructura o disseny del cablejat i dispositius d'una xarxa.

![[topologia.png]]

## Tracer

Eina que serveix per vore el traçat que fan els paquets des del nostre dispositiu fins a l'adreça web desitjada. En el resultat vorem cada "salt" que fa, i que indica un dispositiu.

Alguns dispositius poden no respondre a aquest protocol i no retorna informació.

```
tracert <IP/URL>

tracert 8.8.8.8
tracert google.com
```

![[tracert.png]]
