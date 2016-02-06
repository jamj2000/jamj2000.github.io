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
### Administración de red
<small> IES Luis Vélez de Guevara </small>


# Índice
--- 
#### Interfaces de red
#### Servicios de red
#### Cortafuegos IPTables
#### Proxy + Filtro de contenido

<!--- Note: Nota a pie de página. -->



# Historia
---
#### Proyecto GNU 
#### Kernel Linux


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



# Distros
---
#### Evolución 
#### Listado


## Evolución

[Distribuciones](http://futurist.se/gldt/wp-content/uploads/12.10/gldt1210.svg)


## Listado

![distros](./assets/img/linux-distro-logos.jpg)

[distrowatch.com](http://distrowatch.com)



# Sistemas de archivos
---
#### Formatos 
#### Árbol de directorios


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
#### De texto
#### Gráficas


## Interfaz de texto
- Mediante terminal de texto
- Dos tipos:
 - Terminales virtuales clásicos <!-- .element: class="fragment" data-fragment-index="1" -->
 - Pseudoterminales              <!-- .element: class="fragment" data-fragment-index="2" -->


### Terminales virtuales clásicos 
- Más antiguos
- Normalmente 6 terminales disponibles
- Denominados tty1, tty2, tty3, tty4, tty5 y tty6
- Acceso mediante Ctrl+Alt+F1, Ctrl+Alt+F2, ..., Ctrl+Alt+F6
- Ctrl+Alt+F7 es el entorno gráfico


### Pseudoterminales
- Más modernos
- Pueden crearse muchos pseudoterminales
- Denominados pts/0, pts/1, pts/2, ...
- Acceso desde aplicación gráfica o red


## Interfaz gráfica
- Mediante X-Window (servidor gráfico)
- Muchos escritorios
 - GNOME
 - KDE (Plasma)
 - Unity
 - XFCE
 - LXDE
 - Enlightenment
 - MATE, Cinnamon
 - ...y alguno más



# Comandos
---
#### Conceptos
#### Uso de ayuda
#### Gestión de archivos
#### Gestión de usuarios y permisos
#### Gestión de procesos


## Conceptos
- Innumerables comandos     <!-- .element: class="fragment" data-fragment-index="1" -->
- ... para innumerables usos<!-- .element: class="fragment" data-fragment-index="2" -->
- Muchos comandos externos  <!-- .element: class="fragment" data-fragment-index="3" -->
- ... y pocos comandos internos<!-- .element: class="fragment" data-fragment-index="4" -->


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


## Uso de ayuda
- Páginas de manual, para comandos externos
```sh
man```
- Páginas de ayuda, para comandos internos 
```sh
help
```


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


## Gestión de archivos
### Directorios vs Archivos
- Directorios especiales
```sh 
.   ..   ~   / 
```
- Tipos de archivos 
```sh 
file nombre_archivo 
```
 - Texto plano (txt, html, ...) 
 - Texto con formato (doc, odt, ...)
 - Imágenes (jpg, png, ...)
 - Comprimidos (zip, tar.gz, tgz, ...)
 - . . .


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
cat nombre_archivo
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
Eliminar archivos
```sh
rm archivo1 archivo2 ...
```
Eliminar directorios
```sh
rm -R directorio1 directorio2 ...
```


### Cambiar nombre a archivos o directorios
Cambio de nombre
```sh
mv  nombre_antiguo  nombre_nuevo 
```
También sirve para mover de sitio
```sh
mv  nombre_antiguo  directorio_existente 
```


## Gestión de usuarios y permisos
```sh
chmod 
chown
```


## Gestión de procesos
```sh
ps
top
jobs
fg
bg
kill
```