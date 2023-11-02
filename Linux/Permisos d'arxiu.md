## Teoria

Cada arxiu i directori té un propietari i un grup. Generalment, el propietari és el creador de l'arxiu, i el grup és el grup primari de l'usuari.

Cada arxiu té 3 categories de permís: El propietari de l'arxiu, el grup propietari, i altres.

Cada categoria té tres tipus de permís: 
- Llegir (r)
- Escriure (w)
- Executar (x)

Podem vore els permisos amb ``ls -l`` o ``stat <ARXIU>``.

## Canvis de permisos 

### Mode simbòlic

En el mode simbòlic, escollim 3 opcions: Qui, què i quines.

Qui?
```
u   # Usuari propietari
g   # Grup
o   # Altres (Other)
a   # Tothom (All). Per defecte
```

Què?
```
+   # Afegeix un permís
-   # Elimina un permís
=   # Afegeix un permís, elimina la resta
```

Quines?
```
r   # Llegir (Read)
w   # Escriure (Write)
x   # Executar (eXecute)
t   # Sticky bit (Permisos especials)
```

Exemples
```
chmod o-r <ARXIU>
chmod a+xr <ARXIU>
chmod g=rx <ARXIU>
```

### Mode numèric o Octal

![[permisos_octal.png]]

Numeració de permisos en Octals

```
rw-rw-r-- = 4+2+0 | 4+2+0 | 4+0+0 = 664
rwxr-xr-x = 4+2+1 | 4+0+1 | 4+0+1 = 755
```

Exemples
```
chmod 755 <ARXIU>
chmod 664 <ARXIU>
chmod 777 <ARXIU>
```

## General

Només root pot canviar el propietari d'un arxiu, els usuaris normals poden canviar el grup de l'arxiu si en són el propietari, i a un grup del que siguen membres. root pot canviar el grup de tots els arxius.

Vore tots els permisos en subdirectoris
``ls -lR``

Canviar els permisos de forma recursiva (NO recomanat)
``chmod -R <OCTAL/SIMBÒLIC> <DIRECTORI>``

Canviant els permisos de forma recursiva però específica
```
find ~ -type f -exec chmod 640 {} \;
find ~ -type d -exec chmod 750 {} \;
```

Copiar els permisos d'un arxiu a un altre
``chmod --reference=<ARXIU_A_COPIAR> <ARXIU_A_CANVIAR>

Canviar el propietari d'un arxiu (root obligat):
```
sudo chown <USUARI> <ARXIU>
sudo chown +<USUARI_ID> <ARXIU>
```

Canviar el propietari i el grup d'un arxiu (root obligat):
```
sudo chown <USUARI>:<GRUP> <ARXIU>
```

Canviar el grup d'un arxiu (root obligat):
```
sudo chgrp <GRUP> <ARXIU>
```

Canviar el propietari i/o el grup d'un arxiu de forma recursiva (root obligat)
``sudo chown -R <USUARI>:<GRUP> <DIRECTORI>``

## Permisos especials - SUID (Set User ID)

Quan un executable amb un SUID s'executa, el procés tindrà permisos del propietari del binari, no de l'usuari que executa el comando. Per exemple, quan utilitzem ``cat``, del qual és propietari ``root``, s'executa amb permisos del nostre usuari, no de ``root``. Amb SUID podem canviar això, executant el comando amb permisos del creador del comando (generalment, ``root``).

Si un arxiu té el bit SUID, podrem executar eixe comando amb permisos de ``root``.

Afegir SUID a un arxiu
```
sudo chmod 4<PERMISOS> <ARXIU>
sudo chmod 4755 /usr/bin/cat

sudo chmod u+s <ARXIU>
sudo chmod u+s /etc/bin/cat
````

Eliminar SUID a un arxiu
```
sudo chmod 0<PERMISOS> <ARXIU>
sudo chmod 0755 /usr/bin/cat

sudo chmod u-s <ARXIU>
sudo chmod u-s /etc/bin/cat
```

Trobar tots els arxius amb SUID
``find /usr/bin -perm -4000``

## Permisos especials - SGID (Set Group ID)

Similar a SUID, però amb grups. Si posem un SGID en un directori, tots els arxius i directoris localitzats al seu interior, tindran com a propietari el mateix grup. Molt útil en directoris compartits.

Afegir SGID
```
sudo chmod 2<PERMISOS> <ARXIU>
sudo chmod 2755 /usr/bin/cat

sudo chmod 2<PERMISOS> <DIRECTORI>
sudo chmod 2755 /home/void/Downloads

sudo chmod u+s <ARXIU>
sudo chmod u+s /etc/bin/cat
````

Eliminar SGID a un arxiu
```
sudo chmod 0<PERMISOS> <ARXIU>
sudo chmod 0755 /usr/bin/cat

sudo chmod u-s <ARXIU>
sudo chmod u-s /etc/bin/cat
```

Trobar tots els arxius amb SGID
``find /usr/bin -perm -2000``

## Sticky bit

Aplicat a directoris, permet crear-ne un directori que tothom pot utilitzar com un directori per compartir arxius. Els arxius estan protegits, ja que ningú pot esborrar arxius d'altres.

```
sudo chmod 1<PERMISOS> <DIRECTORI>
sudo chmod 1777 /home/void/Downloads
```

## umask

Determina les opcions d'una màscara que controla quins permisos tenen els arxius i directoris novament creats.

Per defecte, els permisos són 0666 els arxius i 0777 els directoris. El que posem a *umask* serà restat d'eixos permisos. I també per defecte, *umask* és 0002. Així doncs, els arxius novament creats seran 0664, i els directoris, 0775.


Canviar umask
```
umask <4_XIFRES>
umask 0022
```


## Atributs d'arxius

Vore un llistat dels atributs d'arxius
``lsattr``

Canviar atributs d'un arxiu
``sudo chattr +<LLETRA_ATRIBUT> <ARXIU>``

```
e         # Extend format
a         # Append only
c         # Compressed
i         # immutable

Vore més en 'man chattr'
```

