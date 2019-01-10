<!---
Ejemplos de inserción de videos

<video class="stretch" controls><source src="http://clips.vorwaerts-gmbh.de/big_buck_bunny.mp4" type="video/mp4"></video>
<iframe width="560" height="315" src="https://www.youtube.com/embed/3RBq-WlL4cU" frameborder="0" allowfullscreen></iframe>

slide: data-background="#ff0000" 
element: class="fragment" data-fragment-index="1"
-->

## HLC - Fullstack
---
![HLC-Fullstack](http://jamj2000.github.io/hlc-fullstack/hlc-fullstack.png)
<small> 2018-19 - IES Luis Vélez de Guevara - Écija - Spain </small>


## Desarrollo para dispositivos móviles

[![cc-by-sa](http://jamj2000.github.io/hlc-fullstack/cc-by-sa.png)](http://creativecommons.org/licenses/by-sa/4.0/)


## Índice
--- 
- ### Introducción
- ### Desarrollo para móvil
- ### PWA: Manifest.json
- ### PWA: App Shell
- ### PWA: Service Worker
- ### PWA: Despliegue en internet
- ### PWA: Instalación en PC y móvil

<!--- Note: Nota a pie de página. -->



## Introducción


### En esta Unidad aprenderemos a

- Estudiar la tecnología de aplicación web progresiva (PWA).
- Crear el archivo `manifest.json` e idenficar los archivos que conforman el `App Shell`.
- Generar el `Service Worker` y comprobar sus eventos asociados.
- Comprobar el correcto cacheo de los datos.
- Desplegar la aplicación.



## Desarrollo para móvil


### Tipos de desarrollo

- Aplicaciones nativas 
- Aplicaciones híbridas
- Aplicaciones web progresivas (PWA)


### Aplicaciones nativas

- Desarrollada y optimizada específicamente para un sistema operativo determinado.
- Es necesario desarrollar por separado para cada plataforma (Android, iOS, ...)
- Se adapta al 100% con las funcionalidades y características del dispositivo.
- Mayor coste de desarrollo. 
- Es necesario conocer lenguajes como Java, Swift y sus SDKs asociados.
- Existe una tienda centralizada de APPs.


### Aplicaciones híbridas

- Muy versátil, desarrollo web con capacidad de adaptación al dispositivo.
- Rendimiento ligeramente inferior a una aplicación nativa.
- Menor coste de desarrollo que una aplicación nativa.
- Se desarrolla usando HTML5, JS, CSS y posiblemente también parte en Android o Swift.
- Suele usarse algún framework como Cordova, Angular Ionic o React Native.


### Aplicaciones web progresivas

- Desarrollo más sencillo.
- Buen rendimiento, equiparable a una aplicación nativa.
- Mínimo coste de desarrollo.
- Desarrollo multiplaforma real: Web, Escritorio y Móvil.
- Uso de "responsive web design", para adaptar a distintos tamaños de pantalla.
- Es necesario adaptar la aplicación no solo a pantalla de móviles, sino también para PC.
- Todo el desarrollo se realiza en HTML5, JS y CSS.
- 

### Diseño responsive (web adaptativas)

- Framework CSS **Bootstrap**
- Framework CSS **Materialize**



## PWA: manifest.json

**manifest.json**
```json

```

## PWA: App Shell

## PWA: Service Worker

## PWA: Despliegue en internet

## PWA: Instalación en PC y móvil




### Características de las PWA

- **Confiable (Reliable)**. Carga instantánea incluso con condiciones de red inciertas.
- **Rápida (Fast)**. Respuesta rápida a la intereacción con el usuario con animaciones suaves.
- **Compromiso (Engaging)**. Experiencia de usuario inmersiva.

Note: https://developers.google.com/web/progressive-web-apps/


Un Service Worker es como un proxy del lado del cliente y le pone en control de la memoria caché y cómo responder a las solicitudes de recursos. Al pre-almacenar en caché los recursos clave, puede eliminar la dependencia de la red, asegurando una experiencia instantánea y confiable para sus usuarios.

- No hay necesidad de una tienda de aplicaciones. 
- Las aplicaciones web progresivas son instalables y aparecen en la pantalla de inicio del usuario.
- Ofrecen una experiencia de pantalla completa inmersiva.
- Con la ayuda de un archivo de manifiesto de la aplicación web e incluso pueden volver a comprometer a los usuarios con notificaciones push.


El archivo manifest.json de la aplicación permite controlar la apariencia de la aplicación y cómo se inicia. Puede especificar los iconos de la pantalla de inicio, la página que se cargará cuando se inicie la aplicación, la orientación de la pantalla e incluso si desea mostrar o no el navegador Chrome.

Una notificación web push debe ser:

- Oportuna
- Relevante
- y Precisa