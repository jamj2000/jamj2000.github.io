<!---
Ejemplos de inserción de videos

<video class="stretch" controls><source src="http://clips.vorwaerts-gmbh.de/big_buck_bunny.mp4" type="video/mp4"></video>
<iframe width="560" height="315" src="https://www.youtube.com/embed/3RBq-WlL4cU" frameborder="0" allowfullscreen></iframe>

slide: data-background="#ff0000" 
element: class="fragment" data-fragment-index="1"
-->

## Entornos de desarrollo
---
![Entornos de desarrollo](assets/entornosdesarrollo.png)
<small> 2017-18 - IES Luis Vélez de Guevara - Écija - Spain </small>


## Elementos del desarrollo de software

[![cc-by-sa](assets/cc-by-sa.png)](http://creativecommons.org/licenses/by-sa/4.0/)


## Índice
--- 
### Introducción
### Ciclo de vida del software
### Lenguajes de programación

<!--- Note: Nota a pie de página. -->



# Introducción


### En esta Unidad aprenderemos a

- Reconocer la relación de los programas con los componentes del sistema informático.
- Diferenciar código fuente, objeto y ejecutable.
- Identificar las fases de desarrollo de una aplicación informática.
- Clasificar los lenguajes de programación.


### Tipos de software 

- __De sistema__ (Sistema operativo, drivers)
- __De aplicación__ (Suite ofimática, Navegador, Edición de imagen, ...)
- __De desarrollo__ (Editores, compiladores, interpretes, ...)


### Relación Hardware-Software  

- __Disco duro__ :
almacena de forma permanente los archivos ejecutables y los archivos de datos.

- __Memoria RAM__ :
almacena de forma temporal el código binario de los archivos ejecutables y los archivos de datos necesarios.
 
- __CPU__ :
lee y ejecuta instrucciones almacenadas en memoria RAM, así como los datos necesarios.

- __E/S__ :
recoge nuevos datos desde la entrada, se muestran los resultados, se leen/guardan a disco, ...


### Códigos fuente, objeto y ejecutable

- __Código fuente__: archivo de texto legible escrito en un lenguaje de programación.
- __Código objeto__ (intermedio): archivo binario no ejecutable.
- __Código ejecutable__: archivo binario ejecutable. 



# Ciclo de vida del software


### Fases principales del desarrollo

- __ANÁLISIS__  
- __DISEÑO__
- __CODIFICACIÓN__
- __PRUEBAS__
- __MANTENIMIENTO__  

> La disciplina que estudia los principios y metodologías para el desarrollo y mantenimiento de sistemas software se conoce como  __Ingeniería del Software__.


#### __ANÁLISIS__

- Se determina y define claramente las necesidades del cliente y se especifica los requisitos que debe cumplir el software a desarrollar. 
- La especificación de requisitos debe:
  - Ser completa y sin omisiones
  - Ser concisa y sin trivialidades
  - Evitar ambigüedades
  - Evitar detalles de diseño o implementación
  - Ser entendible por el cliente
  - Separar requisitos funcionales y no funcionales
  - Dividir y jerarquizar el modelo
  - Fijar criterios de validación


#### __DISEÑO__

- Se descompone y organiza el sistema en elementos componentes que pueden ser desarrollados por separado. Se especifica la interrelación y funcionalidad de los elementos componentes.
- Las actividades habituales son las siguientes:
  - Diseño arquitectónico
  - Diseño detallado
  - Diseño de datos
  - Diseño de interfaz


#### __CODIFICACIÓN__

- Se escribe el código fuente de cada componente.
- Pueden utilizarse distintos lenguajes informáticos:
  - __Lenguajes de programación__: C, C++, Java, Javascript, ...
  - __Lenguajes de otro tipo__: HTML, XML, JSON, ...


#### __PRUEBAS__

- El principal objetivo de las pruebas debe ser conseguir que el programa funcione incorrectamente y que se descubran defectos.
- Deberemos someter al programa al máximo número de situaciones diferentes.


#### __MANTENIMIENTO__

- Durante la explotación del sistema software es necesario realizar cambios ocasionales, para corregir errores no detectados o para introducir mejoras. Para ello hay que rehacer parte del trabajo realizado en las fases previas.
- Tipos de mantenimiento:
  - __Correctivo__: se corrigen defectos
  - __Perfectivo__: se mejora la funcionalidad
  - __Evolutivo__: se añade funcionalidades nuevas
  - __Adaptativo__: se adapta a nuevos entornos


###  Resultado tras cada fase (I)

- Ingeniería de sistemas: __Especificación del sistema__
- ANÁLISIS: __Especificación de requisitos del software__
- DISENO arquitectónico: __Documento de arquitectura del software__
- DISENO detallado: __Especificación de módulos y funciones__
- CODIFICACIÓN: __Código fuente__


###  Resultado tras cada fase (II)

( Continuación)

- PRUEBAS de unidades: __Módulos utilizables__
- PRUEBAS de integración: __Sistema utilizable__
- PRUEBAS del sistema: __Sistema aceptado__
- Documentación: __Documentación técnica y de usuario__ 
- MANTENIMIENTO: __Informes de errores y control de cambios__


### Modelos de desarrollo de software

- Modelos clásicos
  - Modelo en cascada
  - Modelo en V
- Modelo de construcción de prototipos
  - Prototipos rápidos
  - Prototipos evolutivos
- Modelos evolutivos o incrementales
  - Modelo en espiral
  - Metodologías ágiles


### Modelo en cascada (I)

![Modelo en cascada](assets/cascada.png)


### Modelo en cascada (II)


### Modelo en V (I)

![Modelo en V](assets/v.png)


### Modelo en V (II)


### Prototipos rápidos


### Prototipos evolutivos


### Modelo en espiral (I)

![Modelo en espiral](assets/espiral.png)


### Modelo en espiral (II)


### Metodologías ágiles

- 
- Las más conocidas son:
  - Kanban
  - XP (eXtreme Programming)
  - Scrum


#### __Kanban (I)__

- También se denomina "sistema de tarjetas".
- __Desarrollado inicialmente por Toyota para la industria de fabricación de productos__.
- __Controla por demanda__ la fabricación de los productos necesarios en la cantidad y tiempo necesarios.
- Enfocado a entregar el máximo valor para los clientes, utilizando los recursos justos.
- [Lean manufacturing](https://es.wikipedia.org/wiki/Lean_manufacturing)
- [Kanban en desarrollo software](https://dosideas.com/noticias/metodologias/184-como-usar-kanban-en-el-desarrollo-de-software)
- [LeanKit](https://leankit.com/product-demo/)


#### __Kanban (II)__

![Pizarra kanban](assets/img/kanban-board.png)


#### __XP (Programación extrema)__


#### __Scrum__



# Lenguajes de programación


###  Obtención de código ejecutable

- Para obtener código binario ejecutable tenemos 2 opciones:
  - __Compilar__
  - __Interpretar__


### Proceso de compilación/interpretación

- La compilación/interpretación del código fuente se lleva a cabo en dos fases:
  1. __Análisis léxico__
  2. __Análisis sintáctico__
- Si no existen errores, se genera el código objeto correspondiente.
- Un código fuente correctamente escrito no significa que funcione según lo deseado.
- No se realiza un análisis semántico.


### Lenguajes compilados

- Ejemplos: C, C++
- Principal ventaja: Ejecución muy eficiente.
- Principal desventaja: Es necesario compilar cada vez que el código fuente es modificado.


### Lenguajes interpretados

- Ejemplos: PHP, Javascript
- Principal ventaja: El código fuente se interpreta directamente.
- Principal desventaja: Ejecución menos eficiente.


### JAVA (I)

- Lenguajes compilado e interpretado.
- El código fuente Java __se compila__ y se obtiene un código binario intermedio denominado __bytecode__. 
- Puede considerarse código objeto pero destinado a la máquina virtual de Java en lugar de código objeto nativo. 
- Después este __bytecode__ __se interpreta__ para ejecutarlo.


### JAVA (II)

- Ventajas:
  - Estructurado y Orientado a Objetos
  - Relativamente fácil de aprender
  - Buena documentación y base de usuarios 
- Desventajas:
  - Menos eficiente que los lenguajes compilados 


### Tipos (I)

- Según la forma en la que operan:
  - __Declarativos__: indicamos el resultado a obtener sin especificar los pasos.
  - __Imperativos__: indicamos los pasos a seguir para obtener un resultado.


### Tipos (II)

- Tipos de __lenguajes declarativos__:
  - Lógicos: Utilizan reglas. Ej: Prolog
  - Funcionales: Utilizan funciones. Ej: Lisp, Haskell
  - Algebraicos: Utilizan sentencias. Ej: SQL
- Normalmente son lenguajes interpretados.


### Tipos (III)

- Tipos de __lenguajes imperativos__:
  - Estructurados: C
  - Orientados a objetos: Java
  - Multiparadigma: C++, Javascript
- Los lenguajes orientados a objetos son también lenguajes estructurados. 
- Muchos de estos lenguajes son compilados.


### Tipos (IV)

- Tipos de lenguajes según nivel de abstracción: 
  - Bajo nivel: ensamblador
  - Medio nivel: C
  - Alto nivel: C++, Java


### Evolución

- Código binario
- Ensamblador 
- Lenguajes estructurados 
- Lenguajes orientados a objetos


### Historia simplificada

[Historia simplificada](http://rigaux.org/language-study/diagram-light.png)


### Historia detallada

[Historia detallada](http://rigaux.org/language-study/diagram.png)


### Criterios para la selección de un lenguaje

- Campo de aplicación
- Experiencia previa
- Herramientas de desarrollo
- Documentación disponible
- Base de usuarios
- Reusabilidad
- Transportabilidad
- Imposición del cliente