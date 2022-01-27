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
<p><small> IES Luis Vélez de Guevara - Écija - Spain </small></p>


## Frontend con Svelte

[![cc-by-sa](http://jamj2000.github.io/hlc-fullstack/cc-by-sa.png)](http://creativecommons.org/licenses/by-sa/4.0/)


## Índice
--- 
- ### Introducción
- ### Frameworks
- ### VanillaJS
- ### Componentes web
- ### Svelte
- ### Svelte@next

<!--- Note: Nota a pie de página. -->



## Introducción


### En esta Unidad aprenderemos a

- Utilizar las nuevas características de ECMAScript6. 
- Manipular el DOM.
- Gestionar distintos tipos de eventos.
- Realizar peticiones asíncronas de datos.


### Tipos de aplicaciones

**desde el punto de vista del usuario**

- **MPA** (Mutiple Page Application)
- **SPA** (Single Page Application)


### MPA

![MPA](assets/mpa.png)

- Suelen seguir la arquitectura MVC (Modelo-Vista-Controlador)
- Mayor carga en el servidor.
- Es el servidor el que genera las vistas.

[MVC en Wikipedia](https://es.wikipedia.org/wiki/Modelo%E2%80%93vista%E2%80%93controlador)


### SPA

![SPA](assets/spa.png)

- Se libera de carga al servidor.
- Es el cliente el que genera la vista con los datos que obtiene del servidor.
- Es imprescindible el uso de AJAX.

[SPA en Wikipedia](https://es.wikipedia.org/wiki/Single-page_application)


### Aplicación de ejemplo

**Frontend**

- [TiendaFrontend - Código](https://github.com/jamj2000/tiendafrontend)
- [TiendaFrontend - Demo](http://tiendafrontend.now.sh)

**Backend (API REST)**

- [TiendaBackend - Código](https://github.com/jamj2000/tiendabackend)
- [TiendaBackend - Demo](http://tiendabackend.herokuapp.com)


### Otras aplicaciones de ejemplo

**TiendaW (fullstack)**

- [TiendaW - Código](https://github.com/jamj2000/tiendaw)
- [TiendaW - Demo](http://tiendaw.herokuapp.com)

**Tienda0 (fullstack)**

- [Tienda0 - Código](https://github.com/jamj2000/tienda0)
- [Tienda0 - Demo](http://tienda0.herokuapp.com)


## Frameworks

Los más usados actualmente (Febrero 2020)

- **Angular** (Google) 
- **React** (Facebook)
- **Vue**


### Características generales

![Angular, React, Vue](assets/angular-react-vue.png)

- Frameworks exclusivos para desarrollo Frontend.
- Permiten crear y mantener aplicaciones web de una sola página (SPA).
- Pueden integrarse en Backend de muchos tipos: `nodejs`, `.NET`, `PHP`, ...


### Angular

- De código abierto.
- Desarrollo en **TypeScript**.
- Permite el desarrollo por componentes.
- Mantenido por Google.
- Existe el framework `Angular Ionic` para desarrollo de aplicaciones híbridas para móvil.

[Wikipedia](https://es.wikipedia.org/wiki/AngularJS)


### React

- De código abierto.
- Ofrece un **Virtual DOM**.
- Ofrece un lenguaje específico del contexto llamado **JSX**.
- Permite el desarrollo por componentes.
- Mantenido por Facebook.
- Existe el framework `React Native` para desarrollo de aplicaciones híbridas para móvil.

[Wikipedia](https://es.wikipedia.org/wiki/React)


### Vue

- De código abierto.
- Gran facilidad y simplicidad de uso.
- Ofrece **templates .vue** (HTML, JS y CSS, todo en un archivo).
- Permite el desarrollo por componentes.
- Usado por Xiaomi, Alibaba, Gitlab, ...

[Wikipedia en inglés](https://en.wikipedia.org/wiki/Vue.js)

[Características de Vue](https://www.genbeta.com/desarrollo/por-que-elegir-vuejs-5-razones-para-considerarlo-nuestro-proximo-framework-de-referencia)



## VanillaJS

- Javascript puro, sin uso de frameworks.
- Menor abstracción que usando frameworks.
- Mejor para proyectos pequeños.
- Mejor para aprender el lenguaje JS.
- Manipulación directa del DOM.
- Gestión directa de eventos.


### Descarga 

- VanillaJS es un "framework" muy potente. 😉
- Pesa muy, muy poco.
- Y ofrece muchas funcionalidades.
- Puedes descargarlo desde http://vanilla-js.com/ 


### Uso de API Fetch

- Javascript ya incorpora de serie la posibilidad de **realizar peticiones asíncronas de datos a un servidor**.
- Esta técnica también se conoce como **AJAX**.
- Tradicionalmente se ha usado el objeto **XMLHttpRequest**.
- Una forma más cómoda es usar la moderna **[API Fetch](https://developer.mozilla.org/es/docs/Web/API/Fetch_API/Utilizando_Fetch)**.


#### Fetch - GET ALL

```javascript
fetch(url, { method: "GET" })
.then(res => res.json())
.then(data => {  /* código para éxito */ })
.catch(err => {  /* código para error */ });
```


#### Fetch - GET

```javascript
fetch(url + documento._id, { method: "GET" })
.then(res => res.json())
.then(data => {  /* código para éxito */ })
.catch(err => {  /* código para error */ });
```


#### Fetch - POST

```javascript
fetch(url, {
    method: "POST",
    headers: { "Content-Type": "application/json" },
    body: JSON.stringify(documento)
})
.then(res => res.json())
.then(data => {  /* código para éxito */ })
.catch(err => {  /* código para error */ });
```


#### Fetch - PUT

```javascript
fetch(url + documento._id, {
    method: "PUT",
    headers: { "Content-Type": "application/json" },
    body: JSON.stringify(documento)
})
.then(res => res.json())
.then(data => {  /* código para éxito */ })
.catch(err => {  /* código para error */ });
```


#### Fetch - DELETE

```javascript
fetch(url + documento._id, { method: "DELETE" })
.then(res => res.json())
.then(data => {  /* código para éxito */ })
.catch(err => {  /* código para error */ });
```



## Componentes web

### Definición de componente web

**Parte de una aplicación web que encapsula código HTML, CSS y JavaScript**


### Similitudes

![similitud](assets/similitud.png)


### Desarrollo por componentes (I)

![App](assets/app.png)


### Desarrollo por componentes (II)

![Articulos](assets/articulos.png)


### Desarrollo por componentes (III)

![Clientes](assets/clientes.png)



## Svelte

- Compilador / Framework  para frontend
- Sintaxis sencilla
- Menos líneas de código.
- Ejecución muy eficiente y rápida.
- Pequeño peso de la aplicación final
- Facilita la programación reactiva.

[Apuntes: Frontend con Svelte](https://github.com/jamj2000/tiendafrontend/blob/master/README.md)


### Creación de proyecto

```console
npx  degit  sveltejs/template   nombre-proyecto
cd  nombre-proyecto
tree

├── package.json
├── public
│   ├── favicon.png
│   ├── global.css
│   └── index.html
├── README.md
├── rollup.config.js
└── src
    ├── App.svelte
    └── main.js
```


### Estructura de un componente

```html
<script>

</script>

<style>

</style>

<!-- Nuestros elementos HTML y componentes web -->
```


### Enrutamiento en el cliente

- Svelte no tiene un módulo de enrutamiento oficial.
- Tenemos varios no oficiales.
- Usaremos el módulo de **`svelte-routing`**


#### App.svelte

```html
<script>
  import { Router } from "svelte-routing";
</script>

<Router>
  <Nav />
  <Contenido />
</Router>
```


#### Nav.svelte

```html
<script>
  import { Link } from "svelte-routing";
</script>

<nav>
    <Link to="/">🛒 Inicio</Link>
    <Link to="/articulos">🎁 Artículos</Link>
    <Link to="/clientes">👥 Clientes</Link>
</nav>
```


#### Contenido.svelte

```html
<script>
  import { Route }  from "svelte-routing";
  import Inicio     from "./Inicio.svelte";
  import Articulos  from "./Articulos.svelte";
  import Clientes   from "./Clientes.svelte";
</script>

<main id="contenido">
  <Route path="/"          component={Inicio} />
  <Route path="/articulos" component={Articulos} />
  <Route path="/clientes"  component={Clientes} />
</main>
```


### Código en GitHub

- https://github.com/jamj2000/tiendafrontend



## Svelte@next

- El 19 de Octubre de 2020, Rich Harris (el principal desarrollador de svelte) hace público el video que se enlaza más abajo.
- En él establece las directices para la próxima versión de svelte.

[Rich Harris: Futuristic Web Development](https://youtu.be/qSfdtmcZ4d0)


### Principales novedades

- El framework Sapper no tendrá continuación. Se pretende unificar el proceso de desarrollo.
- Se utiliza **vite** en lugar de **rollup** como empaquetador.
- No es necesario usar *routing*. En lugar de ello se dispone de una ruta **$layout.svelte**.
- Nueva forma de crear un proyecto.
- Estructura de carpetas más coherente.
- Otras novedades.


### Crear el proyecto

```bash
mkdir  nombre-proyecto  &&  cd  nombre-proyecto
npm  init  svelte@next
git  init
```


### Archivos del proyecto

```bash
tree -a  -I .git
.
├── .gitignore
├── package.json
├── README.md
├── snowpack.config.js
├── src
│   ├── app.html
│   ├── components
│   │   └── Counter.svelte
│   └── routes
│       └── index.svelte
├── static
│   ├── favicon.ico
│   └── robots.txt
└── svelte.config.js
```


### Inicializar el proyecto

- Ejecutamos el siguiente comando:

```bash
npm i      # npm  install
```

- Esto instala los módulos indicados en `package.json` y genera archivo de bloqueo `package-lock.json`
- Se instalan las dependencias de desarrollo  (`devDependencies`)
- Si existiesen, se instalararían las dependencias de la aplicación (`dependencies`)


### Desarrollar la aplicación

**npm  run  dev**


### Construir la aplicación

**npm  run  build**


### Estructura de un componente

**Tiene extensión `.svelte`**

```html
<script>

</script>

<style>

</style>

<!-- Nuestros elementos HTML y otros componentes web -->
```


### Archivos de ejemplo


**src/app.html**

```html
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="utf-8">
  <link rel="icon" href="/favicon.ico">
  <meta name="viewport" content="width=device-width, initial-scale=1">
  %svelte.head%
</head>
<body>
  %svelte.body%
</body>
</html>
```


**src/components/Nav.svelte**

```html
<nav>
    <!-- ... ver código fuente en GitHub -->
    <a href="/">🛒 Inicio</a>
    <a href="/articulos">🎁 Artículos</a>
    <a href="/clientes">👥 Clientes</a>
</nav>

<style>
 /* ... ver código fuente en GitHub */
</style>
```


**src/routes/$layout.svelte**

```html
<script>
	import Nav from '$components/Nav.svelte';
</script>

<main>
  <Nav />
  <slot></slot>   <!-- IMPORTANTE -->

  <!-- ... ver código fuente en GitHub  -->
</main>

<style>
  /* ... ver código fuente en GitHub */
</style>
```


**src/routes/index.svelte**

```html
<script>
  import Inicio from '$components/Inicio.svelte';
</script>
	
<Inicio />
```


**src/routes/articulos.svelte**

```html
<script>
  import Articulos from '$components/Articulos.svelte';
</script>

<Articulos />
```


**src/routes/clientes.svelte**

```html
<script>
  import Clientes from '$components/Clientes.svelte';
</script>

<Clientes />
```


### Lista de archivos (I)

```bash
tree -a -I 'node_modules|.git|.svelte'
.
├── .gitignore
├── package.json
├── package-lock.json
├── README.md
├── snowpack.config.js
```


### Lista de archivos (II)

```bash
├── src
│   ├── app.html
│   ├── components
│   │   ├── Articulos.svelte
│   │   ├── Articulo.svelte
│   │   ├── Boton.svelte
│   │   ├── Buscar.svelte
│   │   ├── Clientes.svelte
│   │   ├── Cliente.svelte
│   │   ├── Inicio.svelte
│   │   ├── Nav.svelte
│   │   └── store.js
│   └── routes
│       ├── $layout.svelte
│       ├── articulos.svelte
│       ├── clientes.svelte
│       └── index.svelte
```


### Lista de archivos (III)

```bash
├── static
│   ├── favicon.ico
│   └── robots.txt
└── svelte.config.js
```


### Código en GitHub

[jamj2000/tiendafrontend](https://github.com/jamj2000/tiendafrontend/tree/next)



## EXTRA

**APIs interesantes con las que practicar**

- [JSON Place Holder: Fake API](https://jsonplaceholder.typicode.com/)
- [GitHub API: Documentación](https://docs.github.com/es/rest)
- [Programmable Web: Directorio de APIs](https://www.programmableweb.com/apis/directory)
