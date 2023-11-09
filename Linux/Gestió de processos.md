Una instància d'un programa que està corrent en un ordinador, és un procés i ocupa el seu propi espai en memòria. Quan executem un comando, s'inicia un nou procés.

### Zombie

Quan un procés acaba la seua execució, allibera la majoria de recursos i informació. Quan no ho fa, és un procés zombie. Normalment s'allibera prompte.

### Orfe

Quan un procés pare acaba abans que un procés fill. Per exemple, quan tanquem la terminal però hi ha processos que continuen corrent.

## Llistar processos 

Vore cada procés en la terminal:
``ps``

Vore cada procés en la terminal amb més informació (Full status information):
``ps -f``

Vore tots els processos:
``ps -e``

Vore cada procés en el sistema amb sintaxi standard:
``ps -ef``

Vore cada procés en el sistema amb sintaxi BSD:
``ps aux``

Vore cada procés i ordenar:
```
ps aux --sort=<COLUMNA> | less  # Ordre ascendent
ps aux --sort=%mem | less

ps aux --sort=-<COLUMNA> | less # Ordre descendent
ps aux --sort=-%mem | less
```

Vore tots els processos d'un usuari
```
ps -f -u <USUARI>
ps -f -u root

pgrep -u <USUARI> <PROCÉS>
pgrep -u root sshd
```

Cercar un procés
```
ps -ef | grep <PROCÉS>
ps -ef | grep sshd

pgrep -l <PROCÉS>       # Versió millorada sense falsos positius
pgrep -l sshd
```

Llistar processos en forma d'arbre
``pstree``

Llistar processos i actualitza cada pocs segons
``top``

Opcions de top:
```
h          # Ajuda
Barra Esp  # Refresca
d          # Seleccionar el Delay de refresc
q          # Tancar
u          # Processos d'un usuari
m          # Opcions de memòria
F          # Determinar quines columnes mostrar
```

Fer els canvis permanents, premer ``W`` per "Write" i guardar els canvis.

Alternativa més visual ``sudo apt install htop``

## Matar processos

Llistar les signatures
``kill -l``

Vore tots els processos d'un programa
```
pidof <PROGRAMA>
pidof Firefox
```

Enviar un senyal a un procés
```
kill <PID>  # Per defecte, SIGTERM)
kill 895
```

Enviar un senyal a diversos processos
```
kill -SIGNAL <PID_1>, <PID_1>, <PID_N>
kill -SIGNAL 32, 566, 3462, 564
```

Enviar un senyal específic per PID
```
kill -<SENYAL> <PID>
kill -HUP 3895
```

Recarrega un procés
``kill -1 <ID_PROCÉS>``

Començar un procés immune a SIGHUP
```
nohup <COMANDO> &
nohum wget http://.... &
```

Fluxe normal d'eliminar un procés (Diverses formes)
```
pgrep -l <PROGRAMA>
kill -2 <ID_PROCÉS>

pidof <PROGRAMA>
kill -INT <ID_PROCÉS_1>, <ID_PROCÉS_2>, <ID_PROCÉS_N>

kill -SIGINT $(pidof <PROGRAMA>)
```

Mata totes les instàncies d'un procés
``killall <PROCÉS> ``

Signatures
```
-SIGINT    #  2 - Mata un procés com a usuari (Equivalent a Control + C)
-SIGKILL   #  9 - Mata un procés i no pot ser aturat (Hard kill)
-SIGTERM   # 15 - Mata un procés de forma suau (Soft kill). Per defecte.
```

Llistar treballs que estan en el *bg*
``jobs -l``

Llançar un comando i enviar-ho a segon plànol (per poder continuar utilitzant la terminal)
```
<COMANDO> &
sleep 5 &
```

Pausar el procés actual
*Control + Z*

Enviar al primer plànol i continuar un procés
```
fg <JOB_ID>
fg 1
```

Continuar un procés en el segon plànol
```
bg <JOB_ID>
bg 2
```
