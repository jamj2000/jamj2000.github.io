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
- ### Introducción
- ### Conceptos básicos
- ### Tomcat
- ### JBoss / WildFly
- ### Contenedores Docker

<!--- Note: Nota a pie de página. -->



## Introducción


### En esta Unidad aprenderemos a

- Identificar los principales archivos de configuración y de bibliotecas compartidas.
- Realizar los ajustes necesarios para el despliegue de aplicaciones sobre el servidor.
- Realizar pruebas de funcionamiento y rendimiento de la aplicación Web desplegada.
- Elaborar documentación relativa al despliegue de aplicaciones sobre el servidor de aplicaciones.



## Conceptos básicos


### Ediciones de Java

- **Java Card**
- Micro Edition (**ME**)
- Standard Edition (**SE**)
- Enterprise Edition (**EE**)
- **JavaFX** 


###  Tipos de archivos

- **JAR** (Java ARchive): Es un tipo de archivo que permite almacenar aplicaciones escritas en el lenguaje Java. Los archivos JAR están comprimidos con el formato ZIP y cambiada su extensión a .jar. 

- **WAR** (Web Application aRchive): Es un archivo JAR (con la extensión WAR) usado para distribuir una colección de archivos JSP, servlets, clases Java, archivos XML y contenido web estático (HTML). En conjunto constituyen una aplicación Web.

- **EAR** (Enterprise Application aRchive): Es un formato usado por Java EE para empaquetar en un sólo archivo varios módulos. Permite desplegar varios de esos módulos en un servidor de aplicaciones. Contiene archivos XML llamados descriptores de depliegue que describen cómo realizar dicha operación.



## TOMCAT

**Servidor web y Contenedor de servlets**

![Tomcat](assets/tomcat.png)


### Instalación

```bash
# En Ubuntu 16.04 y 18.04
apt  install  tomcat8   tomcat8-admin

# Opcionalmente puede instalarse también
apt  install  tomcat8-docs  tomcat8-examples
```

Note: Tomcat estará disponible en **http://localhost:8080**


### Configuración

```bash
/etc/tomcat8/
/etc/tomcat8/tomcat-users.xml
```


### Configuración

- Insertamos las siguientes líneas en `/etc/tomcat8/tomcat-users.xml`.

```xml
<role rolename="manager-gui"/>
<role rolename="admin-gui"/>
<user username="tomcat" password="tomcat" roles="manager-gui,admin-gui"/>
```


### Construir webapp

- **Descargamos código fuente**
- **Revisamos los siguientes archivos**

  ```
  <SOURCE>/pom.xml
  <SOURCE>/src/main/resources/applicationContext.xml
  ```


### Construir webapp

- **Construimos con maven**

```bash
mvn  clean  package
```

- **Revisamos los archivos generados**

```
<SOURCE>/target/<APP>.war 
<SOURCE>/target/<APP>/  
```


### Desplegar en tomcat

- **Accedemos a `http://localhost:8080/manager/html`**
- **Seleccionamos archivo `.war` a desplegar.**
- **Y pulsamos en botón desplegar.**


###  Webapps

```bash
/var/lib/tomcat8/
/var/lib/tomcat8/webapps/
/var/lib/tomcat8/webapps/<APP>/WEB-INF/web.xml
/var/lib/tomcat8/webapps/<APP>/WEB-INF/lib/
/var/lib/tomcat8/webapps/<APP>/WEB-INF/classes/
/var/lib/tomcat8/webapps/<APP>/WEB-INF/classes/applicationContext.xml
```


### Webapps

 Directorio principal (raíz): Contendrá los ficheros estáticos (HTML, imágenes, etc...).

-  Carpeta `WEB-INF` : contiene el fichero `web.xml` (descriptor de la aplicación), encargado de configurar la aplicación.
    - Subcarpeta `classes` : contiene los ficheros compilados (servlets, beans).
    - Subcarpeta `lib` : librerías adicionales.
-  Resto de carpetas para ficheros estáticos.



## JBOSS / WILDFLY

**Servidor de aplicaciones**

![WildFly](assets/wildfly.png)



## Contenedores Docker


### docker

![Docker](assets/docker.png)


### docker-compose

![Docker compose](assets/docker-compose.png)