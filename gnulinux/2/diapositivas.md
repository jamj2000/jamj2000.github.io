<!---
Ejemplos

<video class="stretch" controls><source src="http://clips.vorwaerts-gmbh.de/big_buck_bunny.mp4" type="video/mp4"></video>
<iframe width="560" height="315" src="https://www.youtube.com/embed/3RBq-WlL4cU" frameborder="0" allowfullscreen></iframe>

slide: data-background="#ff0000" 
element: class="fragment" data-fragment-index="1"
-->

# GNU/Linux
---
![GNU/Linux](assets/gnulinux.png)
### Administración de red
<small> 2016 - IES Luis Vélez de Guevara - Écija - Spain </small>


# Licencia

[![cc-by-sa](assets/cc-by-sa.png)](http://creativecommons.org/licenses/by-sa/4.0/)

La versión más actualizada de este documento se encuentra en

[jamj2000.github.io](http://jamj2000.github.io/gnulinux/2/diapositivas)


# Índice
--- 
## Introducción
## Configuración estática
## Configuración dinámica
## Servicios de red

<!--- Note: Nota a pie de página. -->



# Intro
---
## Interfaces de red
## Parámetros de red


### Interfaces de red
- Un equipo puede tener varias __interfaces de red__
- Normalmente una sola interfaz de red tiene una única IP.
- A veces una sola interfaz de red puede tener varias IPs.


### Interfaces cableadas

```
eth0, eth1, eth2, ...
eno1, eno2, eno3, ...
enp0s0, enp0s1, enp0s2, ...
```


### Interfaces inalámbricas

```
wlan0, wlan1, wlan2, ...
wlo1, wlo2, wlo3, ...
```


### Parámetros de red

- Dirección IP y máscara 
- Puerta de enlace
- Servidores DNS


### Dirección IP y máscara
- Permite situar la interfaz de red en una red determinada.
- Por ejemplo:
```
192.168.1.2     255.255.255.0
192.168.1.2/24
```


### Puerta de enlace
- Permite dar salida a otra red. 
- Por ejemplo:
```
192.168.1.1
```


### Servidores DNS
- Permite resolver los nombres a direcciones IP.
- Por ejemplo:
```
8.8.8.8
8.8.4.4
```


### Archivo de configuración
- Archivo donde se guardan los parámetros de red.
  - __/etc/network/interfaces__
- Por ejemplo:
```
  # Configuración estática
  auto eth0
  iface eth0 inet static
     address 192.168.1.2
     netmask 255.255.255.0
     gateway 192.168.1.1
     dns-nameservers 8.8.8.8  8.8.4.4
  
  # Configuración dinámica
  auto eth1
  iface eth1 inet dhcp
```


### Servicio de red
- Cada vez que se modifique el archivo anterior debemos reiniciar el servicio de red.
```
/etc/init.d/networking  stop
/etc/init.d/networking  start
```
```
/etc/init.d/networking  restart
```



# C. estática
---
## Interfaces
## IP / Máscara
## Puerta de enlace
## Servidores DNS 


## Interfaces
```
ifconfig -s

ip link show
ip l
```

```                      
ifconfig eth0 down    
ifconfig eth0 up      

ip link set eth0 down
ip link set eth0 up
```


### IP / Máscara
__ifconfig__

```
ifconfig

ifconfig eth0 192.168.1.2 netmask 255.255.255.0    
```

__iproute2__

```                      
ip address show
ip a

ip address add 192.168.1.2/24 dev eth0
```


### Puerta de enlace
__ route__

```
route

route add default gw 192.168.1.1
```

__iproute2__

```
ip route show
ip r

ip route add default via 192.168.1.1
```


### Servidores DNS
```
cat /etc/resolv.conf
```

```
echo "nameserver 8.8.8.8" >> /etc/resolv.conf
echo "nameserver 8.8.4.4" >> /etc/resolv.conf
```



# C. dinámica
---
```
dhclient -r eth0
```

```
dhclient eth0
```



# Servicios de red
---
