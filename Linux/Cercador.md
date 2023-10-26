*Locate és més ràpid que find, ja que utilitza una base de dades prèviament creada, mentres que find cerca en tot el disc dur. Find, però, té més opcions*

## Find

Cerca arxius amb el següent nom
``find / -type -f -name <NOM_ARXIU> 2>/dev/null``

Cerca arxius que en el nom continga la string:
``find / -type -f -name *<NOM_ARXIU>* 2>/dev/null``

Cerca directoris amb el següent nom
``find / -type -d -name <HOME> 2>/dev/null``

Cerca arxius amb el següent nom a partir de l'actual directori
``find . -name <NOM_ARXIU>``

Cerca arxius amb el següent nom, case insentive
``find . -iname <NOM_ARXIU>``

Cerca arxius que comencen amb aquesta string
``find . -name <STRING>*``

Cerca arxius que acaben amb aquesta string
``find . -name **<STRING>``

Cerca arxius que continguen  aquesta string
``find . -name *<STRING>*``

Cerca arxius i elimina'ls
``find . -name <NOM_ARXIU> -delete``

Vore més informació sobre els arxius
``find / -name <NOM_ARXIU> -ls``

Limitar "profunditat" (nivell de carpetes)
``find / -name <NOM_ARXIU> -maxdepth 2``

Cercar per permisos
```
find / -name <NOM_ARXIU> -perm <PERMISOS>
find / -name <NOM_ARXIU> -perm 755
```

Cercar  per tipus
```
find / -type -f -name <NOM_ARXIU> # Cerca arxius
find / -type -d -name <NOM_ARXIU> # Cerca directoris
```

Cercar per mida
```
find / -name <NOM_ARXIU> -size <MIDA>
find / -name <NOM_ARXIU> -size 100k # En torn a 100k
find / -name <NOM_ARXIU> -size +100k # Més de 100k
find / -name <NOM_ARXIU> -size -100k # Menys de 100k
find / -name <NOM_ARXIU> -size +100k -size -200k # Entre
```

Cerca arxius  per data
```
find / -type f -mtime 0 # Fracionat. 12 o 23 hores no és 1 dia = 0
find / type -f -mtime 1 # Modificat entre 1 i 2 dies

find / type -f -atime 0 # Accedit l'últim dia
find / type -f -atime +1 # Accedit fa 2 dies o més
find / type -f -amin -60 # Accedit els últims 60 minuts
```

Cercar per usuari
``find / -type f -user <NOM_USER>``

Cercar per grup
``find / -type f -grup <NOM_GRUP>``

Cerca i executa algun comando
``find / -type f -exec <COMANDO> {} <DETALLS> \;``

Cerca i executa algun comando, preguntant
``find / -type f -ok <COMANDO> {} <DETALLS> \;``

## Locate

Actualitza la base de dades
``sudo updatedb``

Cercar arxiu amb una string al *path*
``locate <NOM_ARXIU>``

Cercar arxiu amb una string al nom
``locate -b <NOM_ARXIU>``

Cercar arxiu amb nom exacte
```
locate -b [<NOM_ARXIU>]
locate -b [s]hadow
```

Cercar arxiu existent (amb independència de la BBDD)
``locate -e <ARXIU>``

Cercar arxiu case-insensitive
``locate -i <ARXIU>``

Cercar amb expressions regulars
``locate -b -r <EXPRESSIONS_REGULAR>``

