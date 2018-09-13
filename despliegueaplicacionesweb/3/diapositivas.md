<!---
Ejemplos de inserción de videos

<video class="stretch" controls><source src="http://clips.vorwaerts-gmbh.de/big_buck_bunny.mp4" type="video/mp4"></video>
<iframe width="560" height="315" src="https://www.youtube.com/embed/3RBq-WlL4cU" frameborder="0" allowfullscreen></iframe>

slide: data-background="#ff0000" 
element: class="fragment" data-fragment-index="1"
-->

## Despliegue de aplicaciones web
---
![Despliegue de aplicaciones web](http://jamj2000.github.io/despliegueaplicacionesweb/despliegueaplicacionesweb.png)
<small> 2018-19 - IES Luis Vélez de Guevara - Écija - Spain </small>


## Servidores de aplicaciones

[![cc-by-sa](http://jamj2000.github.io/despliegueaplicacionesweb/cc-by-sa.png)](http://creativecommons.org/licenses/by-sa/4.0/)


## Índice
--- 
### Introducción


<!--- Note: Nota a pie de página. -->



## Introducción


### En esta Unidad aprenderemos a

- Identificar los principales archivos de configuración y de bibliotecas compartidas.
- Realizar los ajustes necesarios para el despliegue de aplicaciones sobre el servidor.
- Realizar pruebas de funcionamiento y rendimiento de la aplicación Web desplegada.
- Elaborar documentación relativa al despliegue de aplicaciones sobre el servidor de aplicaciones.





En la aplicación J2EE, los módulos se empaquetan como JAR, WAR y EAR en función de su funcionalidad

JAR: los módulos EJB que contienen enterprise java beans (archivos de clase) y el descriptor de despliegue EJB se empaquetan como archivos JAR con extensión .jar (Java Archive)

WAR: los módulos web que contienen archivos de clase Servlet, archivos JSP, archivos compatibles, archivos GIF y HTML están empaquetados como archivo JAR con extensión .war (Web Archive)

EAR: Todos los archivos anteriores (.jar y .war) se empaquetan como archivo JAR con extensión .ear (Enterprise Archive) y se implementan en Application Server.