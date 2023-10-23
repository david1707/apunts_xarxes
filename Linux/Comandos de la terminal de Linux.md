
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

## Datetime

Vore el calendari d'aquest mes
``cal``

Vore el calendari d'un any
``cal <ANY>``

Vore el calendari d'un mes en particular
``cal <MES> <ANY>``

Vore el calendari del mes passat, actual i anterior
``cal 3``

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

## Sistema

Mostra l'espai disponible en els discs durs
``df``

Mostra informació del sistema
```
uname
uname -r
uname -v
uname -p
```

Vore qui és l'actual usuari
``whoami``

Vore qui és l'actual usuari amb més informació
``who``

Cerca arxius amb el següent nom
``find / -type -f -name <NOM_ARXIU> 2>/dev/null``

Cerca directoris amb el següent nom
``find / -type -d -name <HOME> 2>/dev/null``

## Text

Fes un print del text
``echo <TEXT>``

Fes un print d'un arxiu
``cat <ARXIU>``

## Xarxes

Mostrar la configuració de la interfície de xarxes
``ifconfig`` 

Prova la connectivitat d'un web
```
ping <IP>
ping <URL>
ping <IP/URL> -c 5
```


