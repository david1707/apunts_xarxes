
## Arxius

##### Manipulació d'arxius

Crea un arxiu
``touch <NOM_ARXIU>``

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

Vore un arxiu amb *less* (Permet navegació)
``less <ARXIU>``

Vore les últimes 10 línies d'un arxiu
``tail <ARXIU>``

Vore les últimes 3 línies d'un arxiu
``tail -n 3 <ARXIU>``

Vore les noves línies d'un arxiu (en viu, mentres s'edita)
``tail -f <ARXIU>``

Vore les primeres 10 línies d'un arxiu
``head <ARXIU>``

Vore les primeres 4 línies d'un arxiu
``head -n 4 <ARXIU>``

Monitorar canvis en un directori
``watch ls``

Monitorar canvis en un directori cada 3 segons
``watch -n 3 ls``

## Directoris

Crea un directori
``mkdir <NOM_DIRECTORI>``

Crear subdirectoris
``mkdir -p <NOM_DIRECTORI_1>/<NOM_DIRECTORI_2>/<NOM_DIRECTORI_N>``

## Copiar arxius i directoris

Copiar un arxiu
``cp <NOM_ARXIU> <NOM_NOU_ARXIU>``

Copiar un arxiu, mantenint els permisos, propietari, etc.
``cp -p <NOM_ARXIU> <NOM_NOU_ARXIU>``

Copiar arxius i directoris de forma recursiva
``cp -r <DIRECTORI> <DIRECTORI_NOU> ``

## Elimina arxius i directoris

Elimina un arxiu
``rm <NOM_ARXIU>``

Elimina un arxiu amb prompt
``rm -i <NOM_ARXIU>``

Elimina un arxiu, responen "Yes" a cada confirmació
``rm -f <NOM_ARXIU>``

Elimina un arxiu amb verbositat
``rm -v <NOM_ARXIU>``

Elimina un directori
``rm -r <NOM_DIRECTORI>``

**Tot i diguem que rm "elimina" els arxius, el que fa realment és marcar eixe espai en disc com "disponible". No elimina els arxius, simplement els desenllaça**

Elimina realment un arxiu:
``shred -vu -n 100 <ARXIU>``

## Moure arxius i directoris

Moure un arxiu/directori
``mv <ARXIU/DIRECTORI> <NOU_ARXIU/NOU_DIRECTORI>``

Moure diversos arxius
``mv <ARXIU_1> <ARXIU_2> <ARXIU_3><NOU_DIRECTORI>``

Moure tots els arxius amb una mateixa extensió
``mv *.txt <DIRECTORI>``

Moure arxius i pregunta abans de sobre-escriure
``mv -i <ARXIU> <DIRECTORI>``

Moure arxius i ignora preguntar sobre sobre-escriure (no ho fa)
``mv -n <ARXIU> <DIRECTORI>``

Moure arxius només quan l'arxiu origen és més nou que la destinació
``mv -u <ARXIU> <DIRECTORI>``

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

Paregut a tree:
``ls -RF``

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