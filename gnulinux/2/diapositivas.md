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
## Configuración
## Comandos de red
## Servicios de red

<!--- Note: Nota a pie de página. -->



# Intro
---
## Interfaces de red
## Parámetros de red
## Archivos de configuración


### Interfaces de red
- Un equipo puede tener varias __interfaces de red__
- Normalmente una sola interfaz de red tiene una única IP.
- A veces una sola interfaz de red puede tener varias IPs.


### Bucle local
- También se conoce como __loopback__
- Siempre existe.
- Su nombre es __`lo`__
- La dirección IP asociada es __127.0.0.1__
- Aunque podría ser cualquer 127.x.x.x
- No tiene salida a Internet.
- Sirve para pruebas en sitio local.


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
- Ejemplo de dirección IP/máscara:

```
192.168.1.2     255.255.255.0

192.168.1.2/24
```


### Puerta de enlace
- Permite dar salida a otra red. 
- La puerta de enlace suele ser un router.
- Dicho router debe tener al menos 2 interfaces de red.
- E interconectar al menos 2 redes distintas.
- Ejemplo de puerta de enlace:

```
192.168.1.1
```


### Servidores DNS
- Permite resolver los nombres a direcciones IP.
- Obtienen la IP a partir de un nombre.
  - www.google.es --> 216.58.214.163
- Necesarios para la navegación web.
- Ejemplo de servidores DNS:

```
8.8.8.8

8.8.4.4
```


### Archivo de configuración
- Archivo donde se guardan los parámetros de red.
  - __/etc/network/interfaces__
- Ejemplo de archivo de configuración:
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


### Nombres de equipos

- Equipo local: __/etc/hostname__

- Otros equipos: __/etc/hosts__



# Config. de red
---
## Configuración dinámica
## Configuración estática


## Configuración dinámica
---
- Es necesario un servidor DHCP en la red.
- El equipo de usuario realiza 2 operaciones.

```bash
dhclient  -r  eth1    # Liberamos configuración de red

dhclient  eth1        # Renovamos configuración de red 
```


## Configuración estática
---
## Interfaces
## IP / Máscara
## Puerta de enlace
## Servidores DNS 


### Interfaces
__ifconfig__

```bash
ifconfig -s

ifconfig eth0 down 
ifconfig eth0 up    
```

__iproute2__

```bash
ip link show
ip l

ip link set eth0 down
ip link set eth0 up
```


### IP / Máscara
__ifconfig__

```bash
ifconfig

ifconfig eth0 192.168.1.2 netmask 255.255.255.0    
```

__iproute2__

```bash                      
ip address show
ip a

ip address add 192.168.1.2/24 dev eth0
```


### Puerta de enlace
__ route__

```bash
route

route add default gw 192.168.1.1
```

__iproute2__

```bash
ip route show
ip r

ip route add default via 192.168.1.1
```


### Servidores DNS
```bash
cat /etc/resolv.conf
```

```bash
echo "nameserver 8.8.8.8" >> /etc/resolv.conf
echo "nameserver 8.8.4.4" >> /etc/resolv.conf
```



# Comandos
---
- Ver/cambiar nombre de nuestro equipo
- Comprobar conectividad entre 2 equipos
- Ver ruta seguida entre 2 equipos
- Resolución de nombres a IP
- Comprobación de puertos locales
- Comprobación de puertos remotos


### hostname
- Para ver y establecer el nombre de nuestro equipo.
- __Los cambios no son permanentes__.
- Para ello deberíamos editar el archivo __/etc/hostname__
- Ejemplos de uso:

```bash
hostname

hostname portatil
```


### ping
- Comprueba la comunicación entre nuestro equipo y otro equipo remoto.
- Ejemplos de uso:

```bash
ping  192.168.1.1

ping  8.8.8.8

ping  www.yahoo.es
```


### traceroute
- Muestra la ruta entre nuestro equipo y otro equipo destino.
- Ejemplos de uso:

```bash
traceroute  8.8.8.8

traceroute  www.yahoo.es
```


### nslookup
- Comprueba la resolución de nombres a IP.
- Ejemplos de uso:

```bash
nslookup  www.yahoo.es

nslookup  www.yahoo.es  8.8.8.8
```
NOTA: 

Podemos indicar el servidor DNS al que realizar la consulta. 
En este caso 8.8.8.8.


### host 
- Comprueba la resolución de nombres a IP.
- Más cómodo que nslookup.
- Ejemplos de uso:

```bash
host  www.yahoo.es

host  www.yahoo.es  8.8.8.8
```
NOTA: 

Podemos indicar el servidor DNS al que realizar la consulta. 
En este caso 8.8.8.8.


### dig
- Comprueba la resolución de nombres a IP.
- Más opciones que `nslookup`.
- Ejemplos de uso:

```bash
dig  www.yahoo.es

dig  www.yahoo.es  @8.8.8.8
```
NOTA: 

Podemos indicar el servidor DNS al que realizar la consulta. 
En este caso 8.8.8.8.


### netstat
- Comprueba los puertos abiertos en nuestro equipo.
- Ejemplos de uso:

```bash
netstat  -punta

netstat  -tup
```


### nmap
- Comprueba los puertos abiertos en otro equipo.
- Ejemplos de uso:

```bash
nmap  -sP  192.168.1.0/24

nmap  -A -T4  192.168.1.1  192.168.1.10

nmap  192.168.1.1
```



# Servicios
---
- Algunos servicios que pueden implementarse en GNU/Linux.
 - Servidor web          <!-- .element: class="fragment" data-fragment-index="1" -->
 - Servidor FTP          <!-- .element: class="fragment" data-fragment-index="2" -->
 - Servidor DHCP         <!-- .element: class="fragment" data-fragment-index="3" -->
 - Servidor DNS          <!-- .element: class="fragment" data-fragment-index="4" -->
 - Servidor Samba        <!-- .element: class="fragment" data-fragment-index="5" -->
 - Servidor SSH          <!-- .element: class="fragment" data-fragment-index="6" -->
 - Servidor Proxy-caché  <!-- .element: class="fragment" data-fragment-index="7" -->


### Introducción
- __Ver estado__ de un servicio

 ```bash
 service  nombre  status 
 ```

- __Parar/Iniciar__ un servicio

 ```bash
 service  nombre  stop
 service  nombre  start
 ```

- Cada vez que reconfiguramos un servicio debemos __Recargar/Reiniciar__
 
 ```bash
 service  nombre  reload
 service  nombre  restart
 ```


### Introducción
- __Habilitar un servicio en el inicio__

 ```bash
 systemctl  enable  nombre 
 ```

- __Deshabilitar un servicio en el inicio__

 ```bash
 systemctl  disable  nombre
 ```


## Servidor web
![GNU/Linux](assets/apache.png)


### Instalación

```sh
apt-get  install  apache2
``` 

### www
- Las páginas web se almacenan en __/var/www/html__


### Configuración
__/etc/apache2/apache2.conf__
```
...
IncludeOptional mods-enabled/*.load
IncludeOptional mods-enabled/*.conf

Include ports.conf

<Directory /var/www/>
        Options Indexes FollowSymLinks
        AllowOverride None   # None --> All: para soportar rewrite
        Require all granted
</Directory>

AccessFileName .htaccess

IncludeOptional conf-enabled/*.conf
IncludeOptional sites-enabled/*.conf
...
```


### Módulos de Apache
- Permiten ampliar la funcionalidad de Apache
- Archivos de configuración en
 - __/etc/apache2/mods_available/*__
 - __/etc/apache2/mods_enabled/*__


### Instalar módulos
- Para instalar módulos. Ejemplos:
```sh
apt  install  libapache2-mod-php   
apt  install  libapache2-mod-python
apt  install  libapache2-mod-openid
apt  install  libapache2-mod-radius
```

- Para desinstalar módulos. Ejemplos:
```sh
apt  remove  libapache2-mod-radius
```

- Reiniciamos servidor web
```sh
service  apache2  restart
```


### Activar/Desactivar módulos
- Para activar módulos. Ejemplos:
```sh
a2enmod  ssl
a2enmod  rewrite
```

- Para desactivar módulos. Ejemplos:
```sh
a2dismod  ssl
a2dismod  rewrite
```

- Reiniciamos servidor web
```sh
service  apache2  restart
```


### Sitios virtuales en Apache
- Permiten alojar varios sitios
- Archivos de configuración en
 - __/etc/apache2/sites_available/*__
 - __/etc/apache2/sites_enabled/*__


### Crear sitios virtuales
- Es necesario crear un archivo en __/etc/apache2/sites-sites_available/__ para cada sitio.
- En dicho archivo establecemos la configuración del sitio.
- Para activar o desactivar el sitio utilizamos __a2ensite__ / __a2dissite__.


### Activar/Desactivar sitios
- Para activar sitios. Ejemplos:
```sh
a2ensite  default-ssl
a2ensite  mi-sitio
```

- Para desactivar sitios. Ejemplos:
```sh
a2dissite  default-ssl
a2dissite  mi-sitio
```

- Reiniciamos servidor web
```sh
service  apache2  restart
```


### Plataforma LAMP
__L__inux - __A__pache - __M__ySQL - __P__HP

![GNU/Linux](assets/lamp.png)


### Instalación
A partir de Ubuntu 16.04 (con PHP7)
```sh
apt  install  apache2  mysql-server  php  php-mysql  libapache2-mod-php
```
Antes de Ubuntu 16.04 (con PHP5)
```sh
apt-get  install  apache2  mysql-server  php5  php5-mysql
```


### LAMP

- Permite el montaje de portales (CMS o SGC)
 - CMS: Content Management System 
 - SGC: Sistemas Gestores de Contenidos
- Ejemplos de SGC:
 - Joomla
 - Moodle
 - Wordpress
 - Prestashop
 - ownCloud
 - ... y muchos más


### Extensiones de PHP
- Proporciona mayor funcionalidad a las aplicaciones PHP (versión 7).
- Para instalar extensiones. Ejemplos:
```sh
apt  install  php-gd  php-curl  php-mcrypt
```
- Para activar extensiones. Ejemplos:
```sh
phpenmod  gd  curl  mcrypt
```

- Para desactivar extensiones. Ejemplos:
```sh
phpdismod  mcrypt  gd  curl
```

- Reiniciamos servidor web
```sh
service  apache2  restart
```


## Servidor FTP
__F__ile __T__ransfer __P__rotocol

- Un servidor muy utilizado es __vsftpd__
- Un cliente muy utilizado es FileZilla
 - FileZilla soporta FTP, FTPS, FTPES y SFTP


## Servidor DHCP
__D__ynamic __H__ost __C__onfiguration __P__rotocol

Asigna IPs de forma dinámica en una red local

```sh
apt-get  install  isc-dhcp-server
``` 


## Servidor DNS
__D__omain __N__ame __S__ervice

Resuelve Nombres --> IP

```sh
apt-get  install  bind9
``` 


## DDNS = DHCP + DNS
__D__ynamic __D__omain __N__ame __S__ervice

1. Solución 1: Integramos
 - isc-dhcp-server
 - bind9
1. Solución 2: __dnsmasq__
 - mejor solución para LANs
 - archivo de configuración en __/etc/dnsmasq.conf__

```sh
apt-get  install  dnsmasq
```


## Servidor Samba
- Soporte para protocolos __SMB__ y CIFS
- Permite compartición de archivos e impresoras con Windows

![GNU/Linux](assets/samba.png)

### Instalación
```
apt-get  install  samba  smbclient  cifs-utils
```


### Configuración
__/etc/samba/smb.conf__

```
[global]
   workgroup = WORKGROUP
   server string = Servidor SMB/CIFS Linux

   security = user
   map to guest = Bad User

   log file = /var/log/samba/%m.log
   max log size = 50

[documentos]
   comment = "Carpeta compartida sin autenticación"
   path = /public
   public = yes
   only guest = yes
   writable = yes
```
```sh
chown  -R  nobody:nogroup  /public
```


### Comprobaciones

- Comprobamos sintaxis de archivo de configuración

 ```sh
 testparm
 ```

- Comprobamos conexión

 ```sh
 smbclient  -L 192.168.1.1
 ```


### Windows - Mapeo de unidad red
![GNU/Linux](assets/samba-win-map1.png)


![GNU/Linux](assets/samba-win-map2.png)


![GNU/Linux](assets/samba-win-map3.png)


### Linux - Acceso a unidad de red
![GNU/Linux](assets/samba-linux-mount.png)


### Linux - Montaje de unidad de red

```sh
mount   -t cifs   //192.168.1.1/documentos   /mnt/docs
```

- Datos accesibles en carpeta /mnt/docs
- Configuración no permanente.
- Para hacer la configuración permanente, editar __/etc/fstab__

``` 
#Dispositivo              #Punto de montaje  #Tipo   #Opciones                        #Volcado y pasada  
//192.168.1.1/documentos  /mnt/docs          cifs    guest,uid=1000,iocharset=utf8    0  0
```


## Servidor SSH
__S__ecure  __SH__ell

Acceso remoto

![GNU/Linux](assets/openssh.gif)


### Utilidad
- Muy utilizado actualmente para acceso remoto por terminal.
- Más seguro que telnet.
- El tráfico viaja cifrado, cosa que no hace telnet.
- Cualquier comando del terminal de Linux está disponible.
- Con la opción __-X__ se pueden lanzar también aplicaciones gráficas.
- Comandos relacionados:
 - __scp__:   para copia remota
 - __sftp__:  para FTP sobre SSH


### Instalación
```sh
apt-get install ssh
```

### Configuración
__/etc/ssh/sshd_config__
```
...
Port 22
Protocol 2

HostKey /etc/ssh/ssh_host_rsa_key
HostKey /etc/ssh/ssh_host_dsa_key
HostKey /etc/ssh/ssh_host_ecdsa_key
HostKey /etc/ssh/ssh_host_ed25519_key

PermitRootLogin prohibit-password

X11Forwarding yes         # Permite conectar con  ssh -X

Banner /etc/issue
DenyUsers  usuario
...
```


### Conexión a servidor SSH 
```sh
ssh  -X   usuario@servidor
```
### Copia de archivos
```sh
scp  archivos_locales  usuario@servidor:directorio_destino
```
o en sentido inverso
```sh
scp  usuario@servidor:directorio_origen/archivos  directorio_local
```


### SFTP: FTP sobre SSH
![GNU/Linux](assets/sftp.png)


### SSHFS
- SSHFS es un reciente sistema de archivos en red.
- Usa el protocolo SSH.
- Instalación:

 ```sh
 apt-get  install  sshfs
 ```


### Montaje y desmontaje manual
- Para montar usamos el comando __sshfs__

 ```sh
 sshfs  [usuario@]equipo:[dir]  punto_montaje  [opciones]
 ```

- Para desmontar usamos el comando __fusermount__

 ```sh
 fusermount  -u punto_montaje 
 ```


### Montaje y desmontaje automático

- Deberemos editar el archivo __/etc/fstab__.
- Ejemplo de configuración para acceder a particiones compartidas en una Raspberry Pi.

```
## Raspberry SSHFS  ## Modificar /etc/fuse.conf (user_allow_other)
# Dispositivo      # Punto montaje   # Tipo        # Opciones                                        #Volcado y pasada
pi@pi:/mnt/Datos1  /mnt/ssh/Datos1   fuse.sshfs    defaults,allow_other,uid=1000,gid=1000,_netdev    0  0
pi@pi:/mnt/Datos2  /mnt/ssh/Datos2   fuse.sshfs    defaults,allow_other,uid=1000,gid=1000,_netdev    0  0
```


## Servidor Proxy-caché
![GNU/Linux](assets/squid.png)

- El proxy más conocido es __squid__
- Sirve de intermediario entre una LAN y la WWW.
- Suele trabajar en conjunción con un cortafuegos, por ejemplo _iptables_
- A menudo realiza cacheo de páginas, permitiendo
 - reducir el ancho de banda utilizado por la LAN
 - aumentar la velocidad de navegación


### Proxy + Filtro de contenido

![GNU/Linux](assets/squid-dansguardian.png)

- Al proxy puede añadírsele
 - un filtro de contenido, por ejemplo _dansguardian_ 
 - un antivirus en línea, por ejemplo _clamav_
