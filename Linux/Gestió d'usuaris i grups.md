
## Entenent passwd i shadow

Parts de ``/etc/passwd``:
``root:x:0:0:root:/root:/bin/bash``

```
1 - root - Nom
2 - x - Password guardat en /etc/shadow. Si no té x, no necessita password
3 - 0 - User ID
4 - 0 - Group ID
5 - root - Comentari
6 - /root - Directori de home
7 - /bin/bash - Shell per defecte. /nologin o /false = Aquest usuari no pot fer login
```

Parts de ``/etc/shadow``:
``void:$y$j9T$nloCowmx.Zsn5/lh.PVY0/$69SN.Bx7MECnmZQD1DbyspY2Tt2sqdqWHxy16QUguT9:19650:0:99999:7:::``

```
1 - void - Nom
2 - $y$j9.. - Password hashejat. $type$salt$hash
La resta de 7 camps - Referència sobre l'expiració del password. Més en *man shadow*.
```

Parts de ``/etc/group``:

Es pot tindre un grup primari i altres de secundaris.
``adm:x:4:syslog,void``

```
1 - adm - Nom
2 - x - Password guardat en /etc/shadow.
3 - 4 - User ID
4 - syslog,void - Group ID
```

## Gestió de usuaris

Creació d'usuari
```
useradd <NOM_USUARI_NOU>
useradd -m <NOM_USUARI_NOU>    # Crear amb directori personal en /home
passwd <NOM_USUARI_NOU>
```

Creació d'admin
```
useradd -r -s /bin/bash <NOM_USUARI_NOU>
usermod -aG sudo <NOM_USUARI>
```

Elimina un usuari
``deluser <NOM_USUARI>``

Elimina un usuari i els grups als que pertany (si és l'únic membre d'eixe grup)
```
userdel <NOM_USUARI>
userdel -r <NOM_USUARI>         # Elimina usuari i carpeta de /home
```

Vore informació sobre les polítiques d'expiració d'un password
``chage -l <NOM_USUARI>``

## Gestió de grups

Llista els grups de l'usuari actual
``groups``

Llista els grups existents d'un usuari
``groups <NOM_USUARI>``

Mosta informació sobre l'usuari i els seus grups
```
id
id <NOM_USUARI>
```

Vore informació dels grups
```
less /etc/gshadow
less /etc/group
```

Afegir un usuari a un grup
``usermod -c "<COMENTARI>" <NOM_USUARI>    # Comprovar amb grep <USER> /etc/passwd``

Afegir un usuari a un grup secundari
``usermod -aG sudo <NOM_GRUP> <NOM_USUARI>``

Canvia el grup primari d'un usuari
``usermod -G <NOU_GRUP> <NOM_USUARI>        # Comprovar amb groups <USER>``

Crear nou grup
``groupadd <NOM_GRUP_NOU>           # Comprovar amb usermod -G``

Elimina un grup
``groupdel <NOM_GRUP>``

Canvia el nom d'un grup
``sudo groupmod -n <NOM_GRUP_NOU> <NOM_GRUP_VELL>``

## Monitorar els usuaris

*RUID = Real User ID. L'usuari que inicialment fa log in. Mai canvia.
EUID = Effective User ID. L'usuari actual de la shell.*

Vore usuaris logejats
``who -H``

Vore l'usuari actual i els seus grups
``id``

Mostra nom d'usuari real (RUID)
``who``

Mostra nom de l'usuari actual (EUID)
``whoami``

Últims logins
``last``
