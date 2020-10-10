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


## Frontend con VanillaJS

[![cc-by-sa](http://jamj2000.github.io/hlc-fullstack/cc-by-sa.png)](http://creativecommons.org/licenses/by-sa/4.0/)


## Índice
--- 
- ### Introducción
- ### Frameworks
- ### VanillaJS
- ### Componentes web
- ### Svelte

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

**Backend (API RESTful)**

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


## Uso de API Fetch

- Javascript ya incorpora de serie la posibilidad de **realizar peticiones asíncronas de datos a un servidor**.
- Esta técnica también se conoce como **AJAX**.
- Tradicionalmente se ha usado el objeto **XMLHttpRequest**.
- Una forma más cómoda es usar la moderna **[API Fetch](https://developer.mozilla.org/es/docs/Web/API/Fetch_API/Utilizando_Fetch)**.


### Fetch - GET ALL

```javascript
fetch(url, { method: "GET" })
.then(res => res.json())
.then(data => {  /* código para éxito */ })
.catch(err => {  /* código para error */ });
```


### Fetch - GET

```javascript
fetch(url + documento._id, { method: "GET" })
.then(res => res.json())
.then(data => {  /* código para éxito */ })
.catch(err => {  /* código para error */ });
```


### Fetch - POST

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


### Fetch - PUT

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


### Fetch - DELETE

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