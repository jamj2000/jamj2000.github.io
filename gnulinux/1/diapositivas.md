<!---
Ejemplos

<video class="stretch" controls><source src="http://clips.vorwaerts-gmbh.de/big_buck_bunny.mp4" type="video/mp4"></video>
<iframe width="560" height="315" src="https://www.youtube.com/embed/3RBq-WlL4cU" frameborder="0" allowfullscreen></iframe>

slide: data-background="#ff0000" 
element: class="fragment" data-fragment-index="1"
-->

# GNU/Linux
---
![GNU/Linux](./assets/img/gnu-linux.jpg)
### Administración de equipos
<small> IES Luis Vélez de Guevara </small>


# Índice
--- 
## Introducción 
## Sistemas de archivos
## Interfaces de usuario
## Comandos

<!--- Note: Nota a pie de página. -->



# Intro
---
## Proyecto GNU 
## Kernel Linux
## Distribuciones
## Instalación


## Proyecto GNU
- Sistema operativo de tipo Unix.
- Acrónimo recursivo de "GNU's Not Unix"
- Iniciado en 1983 por Richard Stallman.
- Auspiciado por la Free Software Foundation.
- Propio núcleo llamado GNU Hurd.


## Proyecto GNU

![Richard Stallman](./assets/img/RichardStallman.jpg)

Richard Stallman


## Núcleo Linux
- Concebido por Linus Torvalds en 1991.
- Desarrollado por colaboradores de todo el mundo.
- Distribuido bajo licencia GPL (de GNU Public License).
- Uno de los núcleos más ampliamente portados.
- Escrito en el lenguaje de programación C.


## Núcleo Linux

![Linus Torvalds](./assets/img/LinusTorvalds.jpg)

Linus Torvalds


## Distribuciones

- Dos grandes ramas:
 - Basadas en Debian. Paquetes .deb
 - Basadas en RedHat. Paquetes .rpm


## Distribuciones

[Evolución](http://futurist.se/gldt/wp-content/uploads/12.10/gldt1210.svg)


## Distribuciones

![Listado de distros](./assets/img/linux-distro-logos.jpg)

[distrowatch.com](http://distrowatch.com)


## Instalación
Pasos importantes en una instalación:
- Particionado (con instalación de GRUB)
- Creación de usuario



# Sistemas de archivos
---
## Formatos 
## Árbol de directorios


## Formatos
- ext2, ext3, ext4  <!-- .element: class="fragment" data-fragment-index="1" -->
- swap              <!-- .element: class="fragment" data-fragment-index="2" -->
- reiser, btrfs, xfs<!-- .element: class="fragment" data-fragment-index="3" -->
- vfat, exfat, ntfs <!-- .element: class="fragment" data-fragment-index="4" -->
- iso9660, udf      <!-- .element: class="fragment" data-fragment-index="5" -->
- nfs, cifs, smbfs  <!-- .element: class="fragment" data-fragment-index="6" -->
- ... y muchos otros<!-- .element: class="fragment" data-fragment-index="7" -->


## Árbol de directorios

![distros](./assets/img/linux-filesystem.png)



# Interfaces
---
## De texto
## Gráficas


## Interfaz de texto

- Dos tipos:
 - Terminales virtuales clásicos <!-- .element: class="fragment" data-fragment-index="1" -->
 - Pseudoterminales              <!-- .element: class="fragment" data-fragment-index="2" -->


## Terminales virtuales clásicos 
- Más antiguos
- Normalmente 6 terminales disponibles
- Denominados tty1, tty2, tty3, tty4, tty5 y tty6
- Acceso mediante Ctrl+Alt+F1, Ctrl+Alt+F2, ..., Ctrl+Alt+F6
- Ctrl+Alt+F7 es el entorno gráfico


## Pseudoterminales
- Más modernos
- Pueden crearse muchos pseudoterminales
- Denominados pts/0, pts/1, pts/2, ...
- Acceso desde aplicación gráfica o red


## Interfaz gráfica
- Mediante X-Window (servidor gráfico)
- Muchos tipos de escritorios
 - GNOME
 - KDE (Plasma)
 - Unity
 - XFCE
 - LXDE
 - Enlightenment
 - MATE, Cinnamon
 - ...y alguno más



# Comandos (I)
---
## Conceptos
## Uso de ayuda
## Comandos básicos


## Conceptos
- Innumerables comandos     <!-- .element: class="fragment" data-fragment-index="1" -->
- ... para innumerables usos<!-- .element: class="fragment" data-fragment-index="2" -->
- Muchos comandos externos  <!-- .element: class="fragment" data-fragment-index="3" -->
- ... y pocos comandos internos<!-- .element: class="fragment" data-fragment-index="4" -->


## Conceptos
- Comandos externos principalmente en: 
 - /bin
 - /usr/bin
 - /sbin
 - /usr/sbin
- Comandos internos  ¿Dónde?
 - Dentro de /bin/bash


## Uso de ayuda
Para comandos externos, __páginas de manual__
```sh
man```
Para comandos internos, __páginas de ayuda__
```sh
help
```


## Uso de ayuda
Formato de un comando
```
comando  [opciones]  [argumentos]
```
Opciones cortas
```
-h -a -l ...
```
Se pueden agrupar sin un orden
```
-ahl
```
Opciones largas
```
--help  --verbose ...
```
Argumentos
```
nombre_archivo  nombre_directorio  subcomando  ...
```


## Comandos básicos
¿Quién soy?
```sh
whoami
```
Más información
```sh
id
```
¿Dónde estoy?
```sh
pwd
```



# Comandos (II)
---
## Gestión de archivos
## Gestión de usuarios
## Gestión de procesos


## Gestión de archivos


### Directorios vs Archivos
Directorios
```sh 
.   ..   ~   /   /home/usuario
```
Archivos 
 - Archivos regulares
 - Archivos especiales


### Archivos regulares 
```sh 
file nombre_archivo 
```
 - Texto plano (txt, html, ...) 
 - Texto con formato (doc, odt, ...)
 - Imágenes (jpg, png, ...)
 - Comprimidos (zip, tar.gz, tgz, ...)
 - . . .


### Archivos especiales
- Enlaces simbólicos
- Dispositivos de caracteres
- Dispositivos de bloques
- Tubería con nombre
- Socket con nombre


### Desplazarnos por el sistema 
```sh
cd directorio_destino
```
- Ruta absoluta
 - Se inicia en el directorio raíz
 - SIEMPRE comienza por /
 - Es independiente del directorio actual
- Ruta relativa
 - Se inicia en el directorio actual
 - NUNCA comienza por /
 - Depende del directorio actual


### Desplazarnos por el sistema 
Estoy en /home/usuario
```sh
pwd
/home/usuario
```
Me desplazo usando una ruta relativa
```sh
cd Escritorio
pwd
/home/usuario/Escritorio
```
Me desplazo usando una ruta absoluta
```sh
cd /home/usuario/Descargas
pwd
/home/usuario/Descargas
```


### Desplazarnos por el sistema 
Atajo: Voy directo a mi directorio personal
```sh
cd ~
```
Atajo: Lo mismo, pero más sencillo
```sh
cd 
```
Atajo: vuelvo al directorio anterior
```sh
cd -
```


### Listado de un directorio
Listado de directorio actual
```sh
ls
```
Listado de otro directorio
```sh
ls /ruta/absoluta/al/directorio
```
Listado de otro directorio
```sh
ls ruta/relativa/al/directorio
```


### Listado de un directorio
Listado de todo el contenido (incluso oculto)
```sh
ls -a
```
Listado largo
```sh
ls -l
```
Listado largo de todo el contenido
```sh
ls -la
```


### Ver contenido de archivos de texto
```sh
cat  nombre_archivo
more nombre_archivo
less nombre_archivo
nano nombre_archivo
```


### Crear archivos y directorios vacíos
Crear archivos
```sh
touch archivo1 archivo2 ...
```
Crear directorios
```sh
mkdir directorio1 directorio2 ...
```


### Eliminar archivos y directorios (vacíos o no)
```sh
rm      archivo1     archivo2 ...
rm  -R  directorio1  directorio2 ...
```


### Cambiar nombre a archivos o directorios
Cambiar el nombre
```sh
mv  nombre_antiguo  nombre_nuevo 
```
O mover de sitio
```sh
mv  nombre_antiguo  directorio_existente 
```


## Gestión de usuarios


### Entrada al sistema
- Entorno de texto ... mediante __login__
- Entorno gráfico ... mediante __Display Manager__


### Display Managers
- Utilizados antes de cargar el escritorio
- Función equivalente a login para entorno gráfico
- Numerosos Display Managers
 - GDM  (para GNOME)
 - SSDM (para KDE. Antes usaba KDM)
 - LightDM
 - y muchos más


### Salida del sistema
```sh
exit
logout
```


### Alta de usuario
```sh
adduser nombre_usuario
```

### Baja de usuario
```sh
deluser nombre_usuario --remove-home
```


### Cambio de usuario
```sh
su
su nombre_usuario
```


### Elevación de privilegios
```sh
sudo comando
sudo -s
```


### Propietario
Comando chown
```sh
chown    usuario:grupo  archivo
chown -R usuario:grupo  directorio

```


### Permisos
Comando chmod
```sh
chmod    644 archivo
chmod -R 755 directorio
```
[Página en Wikipedia](https://es.wikipedia.org/wiki/Chmod)


### Permisos

Número | Binario | Permisos
------:|:-------:|---------
__`0`__|__`000`__|__`---`__ 
`1`    |`001`    |`--x` 
`2`    |`010`    |`-w-` 
`3`    |`011`    |`-wx` 
__`4`__|__`100`__|__`r--`__ 
__`5`__|__`101`__|__`r-x`__ 
__`6`__|__`110`__|__`rw-`__ 
__`7`__|__`111`__|__`rwx`__ 


## Gestión de procesos


### Tuberias
__comando1 | comando2__

Ejemplos
```sh
cat /etc/passwd | cut -d : -f 1,5,7
cat /etc/passwd | cut -d : -f 1,5,7 | sort 
cat /etc/passwd | cut -d : -f 1,5,7 | sort | less
cat /etc/passwd | cut -d : -f 1,5,7 | grep /bin/.*sh 
ls -l       | tr -s ' ' | cut -d ' ' -f 1,9- 
ls -lR /tmp | tr -s ' ' | cut -d ' ' -f 1,9- | grep ^d
ls -lR /bin | tr -s ' ' | cut -d ' ' -f 1,9- | grep ^...s......
``` 


### Redirecciones
__comando >  archivo__

__comando >> archivo__

Ejemplos
```sh
ls /home/usuario > listado

```


### Segundo plano
__comando &__

Ejemplos


```sh
ps
top
jobs
fg
bg
kill
```
