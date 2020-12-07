<!---
Ejemplos de inserción de videos

<video class="stretch" controls><source src="http://clips.vorwaerts-gmbh.de/big_buck_bunny.mp4" type="video/mp4"></video>
<iframe width="560" height="315" src="https://www.youtube.com/embed/3RBq-WlL4cU" frameborder="0" allowfullscreen></iframe>

slide: data-background="#ff0000" 
element: class="fragment" data-fragment-index="1"
-->

## HLC - PHP
---
![HLC - PHP](http://jamj2000.github.io/hlc-php/hlc-php.png)
<p><small> IES Luis Vélez de Guevara - Écija - Spain </small></p>


## Programación web

[![cc-by-sa](http://jamj2000.github.io/hlc-php/cc-by-sa.png)](http://creativecommons.org/licenses/by-sa/4.0/)


## Índice (I)
--- 
- ### Introducción
- ### Protocolo HTTP
- ### Instalación de servidor web
- ### Estructura de una página HTML


## Índice (II)
--- 
- ### Variables superglobales
- ### Formularios
- ### Cookies
- ### Sesiones

<!--- Note: Nota a pie de página. -->



## Introducción


### En esta Unidad aprenderemos a

- Los conocimientos básicos del funcionamiento HTTP.
- Distinguir entre equipo servidor y equipo cliente.
- Instalar y configurar un servidor web.
- La estructura y etiquetas HTML más utilizadas.
- Trabajar con código HTML, fundamentalmente formularios.
- Trabajar con código PHP ejecutado en el servidor.
- Trabajar con cookies.
- Trabajar con sesiones.



## Protocolo HTTP

![arquitectura HTTP](assets/arquitectura-http.jpg)

- Es un protocolo Cliente-Servidor.
- Es un protocolo Petición-Respuesta.
- Es un protocolo sin estado.
  - No se guarda información de peticiones anteriores.  


### Generación de HTML con PHP

![arquitectura PHP](assets/arquitectura-php.png)

- **El código PHP se ejecuta en el servidor**.



## Instalación de servidor web

- Instalación de servidor web **Apache2 con soporte PHP**

```bash
apt  install  apache2  libapache2-mod-php
```



## Estructura de una página HTML

```html
<!DOCTYPE html>
<html lang="es">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Documento HTML</title>
</head>
<body>
    <!-- Aquí va el cuerpo HTML -->
</body>
</html>
```


## Formularios



## Cookies



## Sesiones

