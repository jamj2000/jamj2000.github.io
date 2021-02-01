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
- ### Servidor web


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
- Es un protocolo sin estado: no se guarda información de peticiones anteriores.  


### Ejecución de PHP

- El código PHP siempre se ejecuta en un **servidor web**.
- El cliente no ve el código PHP, sólo HTML.

![arquitectura PHP](assets/arquitectura-php.png)



## Servidor web

Usaremos Apache2 como servidor web.


### Instalación de servidor web

- Instalación de servidor web **Apache2 con soporte PHP**

```bash
sudo  apt  install  apache2  libapache2-mod-php
```


### Estructura de una página HTML

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



## Variables superglobales

- Son variables internas que están disponibles siempre en todos los ámbitos del script, incluso dentro de las funciones.
- Proporcionan información relevante en la comunicación cliente-servidor.


### Lista de variables

- **$_SERVER**: información sobre parámetros del servidor (nombre del servidor, puerto del usuario,
etc.).
- **$_GET**: datos recibidos desde un formulario por el método GET.  
- **$_POST**: datos recibidos desde un formulario por el método POST.
- **$_REQUEST**: datos recibidos desde un formulario (ya sea GET o POST).
- **$_COOKIE**: datos guardados por el servidor en el PC del usuario.
- **$_SESSION**: datos guardados para su uso a través de múltiples páginas.
- **$_FILES**: ficheros recibidos después de un envío.



## Formularios

- Los formularios HTML **permiten introducir datos** y enviarlos a un servidor web.
- **El servidor se encarga de procesar dichos datos**. Para ello puede usar **PHP**, JSP, Python u otro lenguaje de servidor.


### Ejemplo de formulario (cliente)
```html
<form action='script.php' method='post'>
    <input type='text'   name='dato'/>
    <input type='submit' name='boton' value='Enviar'/>
</form>
``` 
- El atributo **action** del elemento FORM indica la página a la que se le enviarán los datos del
formulario. En nuestro caso se tratará de un script PHP.
- El atributo **method** especifica el método usado para enviar la información. Normalmente será el método post.


### Ejemplo de acción (servidor)

```php
<?php 
  echo "El dato recibido es " . $_POST['dato'] ;
?>
```
- Este código PHP se ejecuta en el servidor web. 
- El cliente, es decir el navegador web, no ve el código PHP, sólo código HTML.



## Cookies


### Introducción

- Las cookies es un método que permite **guardar información en el ordenador del cliente** para recuperarla en el futuro.

- Las cookies permiten que páginas distintas puedan acceder a una variable común, el array asociativo $_COOKIE.


### Crear una cookie

setcookie( *nombre de cookie*, *valor la cookie*, *fecha de expiración*, *carpeta del servidor*);

```php
setcookie("color", "#ff0000", time()+60*60*24*365, "/");
```


### Usar la cookie

$_COOKIE['*nombre de cookie*']

```php
echo $_COOKIE['color'];
```


### Eliminar la cookie

setcookie( *nombre de cookie*, *valor la cookie*, *fecha expirada*, *carpeta del servidor*);

```php
setcookie("color", "#ff0000", time()-1000, "/");
```



## Sesiones


### Introducción

- Las sesiones son un método que permite **guardar información en el servidor** para recuperarla en el futuro.
  
- Las sesiones permiten que páginas distintas puedan acceder a una variable común, el array asociativo $_SESSION.


### Antes de su uso

- En PHP, se deseamos trabajar con variables de sesión, debemos poner al principio de página, antes de cualquier etiqueta HTML, la siguiente sentencia:

```php
session_start();
```


### Crear una variable de sesión

$_SESSION['*nombre de variable*'] = *valor de la variable*;

```php
session_start();
$_SESSION['usuario']=$_REQUEST['campousuario'];
$_SESSION['clave']  =$_REQUEST['campoclave'];
```


### Usar la variable de sesión

echo $_SESSION['*nombre de variable*'];

```php
session_start();
// ...

echo $_SESSION['usuario'];
```