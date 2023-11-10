## Informació d'interfícies 

Mostrar informació sobre les interfícies habilitades
``ifconfig``

Mostrar informació sobre totes les interfícies
```
ifconfig -a
ip address show
```

Mostrar informació sobre una interfície específica
``ifconfig enp0s3``

Mostrar només informació específica de:
```
ip -4 address   # Informació de IPv4
ip -6 address   # Informació de IPv6
```

Mostrar la passarel·la (Dispositiu que interconnecta xarxes de arquitectures/protocols diferents)
``route``
Mostrar la passarel·la de forma numèrica
``route -n``

Mostrar els servidors DNS
``resolvectl status``

## Modificar interfícies

Deshabilitar una interfície
``ifconfig enp0s3 down``

Habilitar una interfície
``ifconfig enp0s3 up``

Configurar una IP en una interfície
``ifconfig enp0s3 192.168.0.222/24 up``

Configurar una adreça IP secundària
``ifconfig enp0s3 10.0.0.1/24``

Eliminar i afegir una passarel·la (Gateway) nova
```
route del default gw 192.168.0.1
route add default gw 192.168.0.2
```

Canviar l'adreça MAC
```
ifconfig enp0s3 down
ifconfig enp0s3 hw ether 00:00:00:00:00:00
ifconfig enp0s3 up
```

Canviar l'adreça MAC
``ip link set dev enp0s3 adress 00:00:00:00:00:00``

## Netplan

Network manager
```
sudo systemctl stop NetworkManager
sudo systemctl disable NetworkManager
sudo systemctl enable NetworkManager
sudo systemctl status NetworkManager
sudo systemctl is-enabled NetworkManager
```

Aplicar els canvis
``sudo netplan apply``

Comprovar la configuració
``ifconfig``

Creació d'IP estàtica

```
sudo systemctl stop NetworkManager
sudo systemctl disable NetworkManager
sudo systemctl status NetworkManager
sudo systemctl is-enabled NetworkManager

# Create a YAML file in /etc/netplan

network:
  version: 2
  renderer: networkd
  ethernets:
    enp0s3:
    dhcp4: false
    addresses:
      - 192.168.0.20/24
     gateway4: "192.168.0.1"
     nameservers:
     addresses:
       - "8.8.8.8"
       - "8.8.4.4"


sudo netplan apply
ifconfig
```

Opcions de ping
```
ping -c 4       # Fa ping 4 vegades
ping -i 0.4     # Fa ping cada 0.4 segons
ping -q         # Només mostra el resum (Quiet)
ping -t 3       # Time to Live màxim = 3
```

Comprovar que tot va bé en el nostre dispositiu
```
route -a 
ping X.X.X.X    # Anar fent ping per totes les parts fins trobar l'error
```