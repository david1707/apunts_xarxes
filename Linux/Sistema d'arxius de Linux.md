

![[FHS_Linux.png]]


## /

El directori *root* o arrel. Aquest marca l'inici del sistema d'arxius de Linux i és el nivell més alt.

## /bin

Conté binaris o arxius executables disponibles per tots els usuaris. Bin ve de *Binary*

## /boot

Conté arxius requerits per iniciar el sistema. Normalment NO el toquem.

## /dev

Conté arxius de dispositius connectats, generats la majoria durant l'inici del SO o sobre la marxa (quan connectem un USB, per exemple).

## /etc

Literalment, etc. És una mena de carpeta abocador/miscel·lània d'arxius del sistema, arxius de configuració, etc. Podem trobar des dels passwords fins a com configurar un servidor de xarxes, o fins i tot un servidor d'email.

És millor no tocar aquest directory. O fins i tot, fer una còpia de seguretat.

## /home

On trobem els directoris de cada usuari (Per exemple, per la usuària Anna i Robert, tindrem ``/home/anna`` i ``/home/robert``). L'administrador *root* té el seu propi sistema.

## /lib

Conté biblioteques (El nom ve de **lib**rary) de diferents aplicacions. El gestor de paquets controla i gestiona aquest directori.

## /media

Aquest directori és on discs durs externs (com ara, un USB) són muntats una vegada els connectem.

## /mnt

Similar a ``/media``, però actualment no s'utiliza. Ací podem trobar els lectors de CD/DVD.

## /opt

Software propietari que no utilitza els estàndards d'estructura de Linux.

## /proc

Conté informació sobre el teu ordinador: CPU, RAM, Kernel, etc. Generats a l'iniciar l'ordinador.

## /root

El directori de *root*. Té una estructura diferent al del directori de cada usuari en ``/home``.

## /run

Relativament nou, és un sistema d'arxius temporal que funciona amb la memòria RAM. Els continguts desapareixen al reiniciar/apagar l'ordinador.

## /sbin

Conté aplicacions que només el superusuari (d'ahi ve á ``s`` de ``/sbin``) pot utilitzar.

## /sys

Conté informació sobre dispositius, drivers i kernels. Aquesta carpeta la gestiona Linux directament.

## /srv

Conté informació sobre serveis.

Aquesta carpeta la gestiona Linux directament.

## /tmp

Conté arxius temporals, normalment creats per aplicacions en funcionament.

Tot arxiu es eliminat al reiniciar/apagar l'ordinador.

## /usr

Aquest directory conté biblioteques, binaris i documentació dels programes instal·lats, que són compartits entre els diferents usuaris.

## /var

Arxius de i amb variables, com logs que registren esdeveniments(events) que passen en el sistema. Per exemple, ``/var/log/auth.log``

