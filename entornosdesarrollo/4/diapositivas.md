<!---
Ejemplos

<video class="stretch" controls><source src="http://clips.vorwaerts-gmbh.de/big_buck_bunny.mp4" type="video/mp4"></video>
<iframe width="560" height="315" src="https://www.youtube.com/embed/3RBq-WlL4cU" frameborder="0" allowfullscreen></iframe>

slide: data-background="#ff0000" 
element: class="fragment" data-fragment-index="1"
-->
## Entornos de desarrollo
---
![Entornos de desarrollo](assets/entornosdesarrollo.png)
<small> 2017-18 - IES Luis Vélez de Guevara - Écija - Spain </small>


## Optimización y documentación

[![cc-by-sa](assets/cc-by-sa.png)](http://creativecommons.org/licenses/by-sa/4.0/)


## Índice
--- 
### Introducción
### Optimización
### Documentación
### Control de versiones

<!--- Note: Nota a pie de página. -->



## Introducción


En esta Unidad aprenderemos a:

- Trabajar de forma habitual con un sistema de control de versiones.  
- Identificar los patrones de refactorización más usuales.
- Revisar el código fuente usando un analizador de código.
- Documentar el código fuente.



### Herramientas básicas


### Automatización 

Construir (Build) = Compilar + Enlazar


### Ejemplos de constructores

- C: __make__
- Java: maven, ant 



## Optimización


### Hediondez del código

- También llamado __code smell__ en inglés
- Es síntoma en el código fuente que indica posiblemente un problema más profundo.
- Usualmente no son bug de programación (errores): no son técnicamente incorrectos y en realidad no impiden que el programa funcione correctamente. 
- Indica deficiencias en el diseño que puede ralentizar el desarrollo o aumentan el riesgo de errores o fallos en el futuro.
- Es un motivo importante para realizar refactorización.
- [Hediondez del código](https://es.wikipedia.org/wiki/Hediondez_del_c%C3%B3digo)


### Análisis de código

- Tipos:
  - Análisis estático (__lint__)
  - Análisis dinámico (unit tests)


### (Linter) Analizador estático

- [Introducción a los linters -en inglés-](https://github.com/mcandre/linters)


### Ejemplos de linters

- C: lint
- Java: sonar
- Javascript: JSLint, ESLint 
- Multilenguaje: SonarQube


### Refactorización

- Es el proceso de reestructurar un código fuente, alterando su estructura interna sin cambiar su comportamiento externo. 
- Técnicas:
  - Renombrado de variables
  - Pasar código duplicado a funciones
  - ...


## Documentación

- Javadoc
- Gitbook



## Control de versiones


### Sistemas más conocidos:
  - CVS
  - Subversion
  - Mercurial
  - Git


### Git

