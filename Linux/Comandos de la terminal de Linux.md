
[[Arxius i Directoris]]
[[Sistema d'arxius de Linux]]

## Dreceres de teclat en la terminal

Obre una terminal
``Control + Alt + T``

Neteja la terminal (``clear``)
``Control + L``

Tanca la terminal (``exit``) 
``Control + D``

Elimina la línia actual (tot a l'esquerra del cursor)
``Control + U``

Mou el cursor a l'inici de la línia
``Control + A``

Mou el cursor al final de la línia
``Control + E``

Atura el comando que està corrent
``Control + C``

Envia a dormir el comando que està corrent
``Control + Z``

Desperta el comando dormit
``fg``

## Actualitzacions del sistema

Actualitza el llistat de paquets disponibles (no instal·la res)
``sudo apt-get update``

Descarrega i instal·la les actualitzacions
``sudo apt-get upgrade``

Cerca paquets
``sudo apt search <PARAULA>``

## Accés a l'usuari root

Crear password per l'usuari root (Necessari a l'instal·lar un SO nou)
``sudo passwd root``

Canviar password d'usuari
``passwd username``

Ser usuari root temporal (si l'usuari té permís per ser-ho)
``sudo su``

Llançar un comando amb privilegis de root
``sudo <COMANDO>``

## Ajuda, manuals, etc

Ajuda d'un comando
``<COMANDO> --help``

Manual d'un comando (Més extens que l'ajuda, documentació oficial)
``man <COMANDO>``

Navegació dins de ``man``
```
Control + F = Forward
Control + B = Backward
/<PARAULA> = Cercador intern
n = Next
```

Comprova si un comando és un executable o un comando de shell
```
type rm = és un arxiu
type cd = és un comando o shell builtin
```

## Comparar arxius

Compara dos arxius
``cmp <ARXIU_1> <ARXIU_2>``

Compara línia a línia
``diff <ARXIU_1> <ARXIU_2>``

Compara línia a línia en dues columnes
``diff -y <ARXIU_1> <ARXIU_2>``

Comparar hashes
``sha256sum <ARXIU_1> <ARXIU_2>


## Comprimir i arxivar arxius

Arxiva i comprimeix amb tar
``sudo tar -czvf <NOM>.tar.gz <DIRECTORI>``

Arxiva i comprimeix més, però més lent
``sudo tar -cjvf <NOM>.tar.bz2 <DIRECTORI>``

Arxiva i comprimeix multiples carpetes i arxius
``sudo tar -czvf <NOM>.tar.gz <DIRECTORI_1> <ARXIU_1>``

Extraure
``tar -xzvf/-xjvf <ARXIU>``

Mostra els arxius dins de la compressió
``tar -tf <ARXIU>``

Més opcions
```
--exclude='.mkv' --exclude='.avi'   # Exclueix aquest tipus d'arxius
-C <DIRECTORI>                      # Especifica la carpeta d'extracció
```

## Datetime

Vore el calendari d'aquest mes
``cal``

Vore el calendari d'un any
``cal <ANY>``

Vore el calendari d'un mes en particular
``cal <MES> <ANY>``

Vore el calendari del mes passat, actual i anterior
``cal 3``

## Grep

Cerca d'un text a un arxiu
``cat <ARXIU> | grep <TEXT_A_CERCAR>``
##### Opcions

```
-n      # Mostra el número de línia
-i      # Case insensitive
-v      # Invertir la cerca
-w      # Cerca la paraula completa
-a      # Cerca en arxius binaris
-R      # Mostra en el directori de forma recorrent
-c      # Mostra només el número de trobats
```

## Històric

Vore els últims comandos escrits
```
history
cat .bash_history
```

Vore quants comandos guarda en l'arxiu del històric
``echo $HISTFILESIZE``

Vore quants comandos guarda en la memòria
``echo $HISTSIZE``

Corre un comando del llistat de ``history``:
``!<NUMERO>``

Corre el Xé comando del  llistat
``!-2 # Llançaria el penultim comando``

Corre l'últim comando enviat
``!!``

Corre l'últim comando enviat de tipus X (perillós)
``!<COMANDO>

Mostra l'últim comando enviat de tipus X (segur)
``!<COMANDO>:p``

Funció de cercador de comandos per text
``Control + R``

Elimina una línia del històric
``history -d <NUMERO_DE_LÍNIA>``

Elimina tot l'històric
``history -c``

Llança un comando sense que es guarde en l'històric
`` <COMANDO> # Cal simplement prefixar el comando amb un espai en blanc``

Algunes distribucions Linux ignora l'espai en blanc anterior i **SÍ** guarda els comandos amb espai en blanc. 
```
echo $HISTCONTROL # Mostrarà 'ignoreboth' si no guarda un comando amb un espai en blanc, 'ignoredups' si ignora duplicats (i, al no tindre 'ignoreboth', si que guardaria comandos amb un espai en blanc)

HISTCONTROL=ignoreboth # Açò farà que no guarde res amb espais en blanc
```

Afegir un *timestamp* als comandos del històric
``echo 'HISTTIMEFORMAT="%d/%m/%y %T "' >> .bashrc``

## Inode

Enllaçar 2 arxius:
``ln <ARXIU_1> <ARXIU_2>``

Llistar arxius amb el inode:
``ls -n``

Cercar tots els arxius amb el mateix inode
``find / -inum <INODE>``

Crear un symlink (o accés directe)
``ln -s <ARXIU_A_ENLLAÇAR> <NOM_ACCÉS_DIRECTE>``

## Pipes

Combinació de dos o més comandos

```bash
ls -ls | head
ls -ls | head -n 10 | tail -n 1
```

## Redirecció

Fer un comando i guardar a un arxiu
```
<COMANDO> > <ARXIU>
ls -ls > llistat.txt
```

Fer un comando, guardar a un arxiu, i mostra per pantalla
```
<COMANDO> | tee <ARXIU>
ls -ls | tee llistat.txt
```

Fer un comando, afegeix a un arxiu, i mostra per pantalla
```
<COMANDO> | tee -a <ARXIU>
ls -ls | tee -a llistat.txt
```

Fer un comando i afegint el text a un arxiu
``<COMANDO> >> <ARXIU>``

Guarda els missatges d'error
``<COMANDO> 2> <ARXIU>``

Mostra els missatges d'error i èxit
``<COMANDO> 2>&1 <ARXIU>``

## Sistema

Mostra l'espai disponible en els discs durs
``df``

Mostra informació del sistema
```bash
uname
uname -r
uname -v
uname -p
```

Vore qui és l'actual usuari
``whoami``

Vore qui és l'actual usuari amb més informació
``who``

Vore l'usuari actual i informació de grups
``id``

## Tallar

Exemples
```bash
cut /etc/passwd | cut -d ":" -f1 
":" delimita el patró de separació o tall
-f1 indica el camp que volem agafar
```

## Text

Fes un print del text
``echo <TEXT>``

Fes un print d'un arxiu
``cat <ARXIU>``

Compta quantes línies, paraules i caràcters hi ha a un arxiu
``wc <ARXIU>``
## Xarxes

Mostrar la configuració de la interfície de xarxes
``ifconfig`` 

Prova la connectivitat d'un web
```
ping <IP>
ping <URL>
ping <IP/URL> -c 5
```


