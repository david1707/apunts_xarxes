
Modes: Command, Insert i Last Line

Obrir arxius:
```
vim <ARXIU>                     # Obre una instància de VIM
vim <ARXIU_1> <ARXIU_2>         # Obre dos arxius en diferents pàgines
vim -o <ARXIU_1> <ARXIU_2>      # Obre dos arxius apilats
vim -d <ARXIU_1> <ARXIU_2>      # Obre dos arxius en columnes
vimdiff <ARXIU_1> <ARXIU_2>     # Obre dos arxius en columnes
```


Tornar al mode Command:
``Esc``

Command mode:
```
x          # Elimina el caràcter sota el cursor
dd         # Talla la línia actual
5dd        # Talla 5 línies
ZZ         # Guarda i tanca
u          # Desfer
gg         # Moure a l'inici de l'arxiu
G          # Moure al final de l'arxiu
$          # Moure al final de la línia
:n         # Mou a la línia 'n'
Shift + v  # Selecciona la línia actual
y          # Copia al portapapers
p          # Pega després del cursor
P          # Copia abans del cursor
/string    # Cerca la string cap a davant
?string    # Cerca la string cap a darrere
n          # Següent ocurrència
N          # Prèvia ocurrència
*          # Cercar la següent paraula igual a la del cursor
:n         # Següent arxiu (treballant amb més d'un arxiu)
:prev      # Anterior arxiu (treballant amb més d'un arxiu)
Ctl + W    # Canviar de finestra (treballant amb més d'un arxiu)
```

Iniciar el mode Insert
``i``

Insert mode
```
i          # Inserir abans del cursor
I          # Inserir a l'inic de la línia
a          # Inserir després del cursor
A          # Inserir al final de la línia
o          # Inserir a la línia següent
O          # Inserir a la línia anterior
```

Iniciar el mode Last Line
``:``

Last Line mode
```
w!         # Guardar arxiu
q!         # Tancar sense guardar
wq!        # Guarda i tanca
e!         # Desfer fins l'ultima versió guardada
!<COMAND>  # Llança un comando en la terminal, Enter per tornar a Vim
set nu     # Fixar el número de línia
set nonu   # Deixar de fixar el número de línia
syntax on  # Colors
syntax off # Blanc i negre
```

Tutorial de VIM:
``vimtutor``

