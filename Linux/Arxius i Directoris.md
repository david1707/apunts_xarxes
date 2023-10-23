
## Arxius

##### Manipulació d'arxius

Crea un arxiu
``touch <NOM_ARXIU>``

Elimina un arxiu
``rm <NOM_ARXIU>``

Descarrega un arxiu
``wget <URL>``

##### Mostrar arxius

Vore el tipus d'arxiu que és
``file <ARXIU>``

Fer un print d'un arxiu
``cat <ARXIU>``

Fer un print d'un arxiu amb numeració per línia
``cat -n <ARXIU>``

Concatenar un o més arxius
``cat <ARXIU_1> <ARXIU_2> <ARXIU_N> > <NOU_ARXIU>``



## Directoris

Crea un directori
``mkdir <NOM_DIRECTORI>``

Elimina un directori
``rm -r <NOM_DIRECTORI>``

## Navegació

Mostra (print) l'actual directori
``pwd``

Canvia de directori
``cd <RUTA>``

Llistar el contingut d'un directori
```
ls
ls -a             Fitxers ocults
ls -la            Format llarg
ls -X             Ordena alfabèticament per extensió
ls -1             Llistat en una única columna
ls -R             Mostra els arxius de forma recursiva
ls <RUTA>
ls <RUTA> <RUTA> 
```

Mostrar la distribució de carpetes de dalt a baix
``tree``

Mostrar la ruta d'un comando
``which <COMANDO>``

## Timestamps

**Totes les dates són a partir de *epoch* (1 de gener de 1970).**

Vore quan es va accedir, modificar, canviat i creat un arxiu
``stat <ARXIU>``

Llistar per temps de modificació
``ls -lt``

Llistar per temps d'accés
``ls -lu``

Llistar per temps de canvi
``ls -lc``

El timestamp sencer
``ls -l --full-time``

Modifica les dades d'accés i modificació
```
touch -a -t <TIMESTAMP> <ARXIU> # Accés
touch -m -t <TIMESTAMP> <ARXIU> # Modificat
touch -c -t <TIMESTAMP> <ARXIU> # Accés i Modificat

touch -a -t 201110301530.45 linux.txt
```

Copia els timestamps d'un arxiu a un altre
``touch <ARXIU_A_MODIFICAR> -r <ARXIU_TIMESTAMPS_A_COPIAR>`` 

Llistar i ordenar per temps de canvi (metadades), nous primers
``ls -lt``

Llistar i ordenar per temps de modificació (contingut), nous primers
``ls -lt``

Llistar i ordenar per nom, mostrant temps d'accés
``ls -lu``

Llistar i ordenar per temps d'accés, nous primers
``ls -ltu``

Llistar i ordenar per temps d'accés, nous últims
``ls -ltu --reverse``

Llistar, mostrant si és un arxiu o un directori
``ls -F``

Vore permisos del directori
``ls -ld <DIRECTORI>``