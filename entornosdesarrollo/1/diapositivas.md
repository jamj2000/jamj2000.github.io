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

__Disco duro__ :
almacena de forma permanente los archivos ejecutables y los archivos de datos.

__Memoria RAM__ :
almacena de forma temporal el código binario de los archivos ejecutables y los archivos de datos necesarios.
 
__CPU__ :
lee y ejecuta instrucciones almacenadas en memoria RAM, así como los datos necesarios.

__E/S__ :
recoge nuevos datos desde la entrada, se muestran los resultados, se leen/guardan a disco, ...


### Códigos fuente, objeto y ejecutable

- Código fuente: archivo de texto legible escrito en un lenguaje de programación.
- Código (intermedio) objeto: archivo binario no ejecutable.
- Código ejecutable: archivo binario ejecutable. 



# Ciclo de vida del software


### Fases principales del desarrollo de software

- __ANÁLISIS__  
- __DISEÑO__
- __CODIFICACIÓN__
- __PRUEBAS__
- __MANTENIMIENTO__  


#### ANÁLISIS


#### DISEÑO


#### CODIFICACIÓN

Lenguajes informáticos

  - __Lenguajes de programación__: C, C++, Java, Javascript, ...
  - __Lenguajes de otro tipo__: HTML, XML, JSON, ...


#### PRUEBAS


#### MANTENIMIENTO

- __Correctivo__: se corrigen defectos
- __Perfectivo__: se mejora la funcionalidad
- __Evolutivo__: se añade funcionalidades nuevas
- __Adaptativo__: se adapta a nuevos entornos


###  Resultado tras cada fase

Ingeniería de sistemas: __Especificación del sistema__
ANÁLISIS: __Especificación de requisitos del software__
DISENO arquitectónico: __Documento de arquitectura del software__
DISENO detallado: __Especificación de módulos y funciones__
CODIFICACIÓN: __Código fuente__
PRUEBAS de unidades: __Módulos utilizables__
PRUEBAS de integración: __Sistema utilizable__
PRUEBAS del sistema: __Sistema aceptado__
Documentación: __Documentación técnica y de usuario__ 
MANTENIMIENTO: __Informes de errores y control de cambios__


### Modelos de desarrollo de software

- Modelo en cascada
- Modelo en cascada con realimentación
- Modelos evolutivos
  - Modelo de prototipos
  - Modelo en espiral
  - Metodologías ágiles


### Modelo en cascada

![Modelo en cascada](assets/cascada.png)


### Modelo en cascada con realimentación


### Modelos evolutivos


### Modelo de prototipos


### Modelo en espiral


### Metodologías ágiles



# Lenguajes de programación


###  Obtención de código ejecutable

Para obtener código binario ejecutable tenemos 2 opciones
- __Compilar__
- __Interpretar__


### Lenguajes compilados

- Ejemplos: C, C++
- Ventajas:
  - Muy eficientes
- Desventajas:
  - Ejecución y depuración después de compilar


### Lenguajes interpretados

- Ejemplos: PHP, Javascript
- Ventajas:
  - Ejecución y depuración directa
- Desventajas:
  - Menos eficientes


### JAVA (I)

- Lenguajes compilado e interpretado
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

Tipos de __lenguajes declarativos__:
  - Lógicos: Utilizan reglas. Ej: Prolog
  - Funcionales: Utilizan funciones. Ej: Lisp, Haskell
  - Algebraicos: Utilizan sentencias. Ej: SQL

Normalmente son lenguajes interpretados


### Tipos (III)

Tipos de __lenguajes imperativos__:
  - Estructurados: C
  - Orientados a objetos: Java
  - Multiparadigma: C++, Javascript

Los lenguajes orientados a objetos son también lenguajes estructurados. 

Muchos de ellos son lenguajes compilados


### Tipos (IV)

Tipos de lenguajes según nivel de abstracción: 
  - Bajo nivel: ensamblador
  - Medio nivel: C
  - Alto nivel: C++, Java


### Evolución

- Código binario
- Ensamblador 
- Lenguajes estructurados 
- Lenguajes orientados a objetos


### Historia (I)

[Historia simplificada](http://rigaux.org/language-study/diagram-light.png)

[Historia detallada](http://rigaux.org/language-study/diagram.png)


### Criterios para la selección de un lenguaje

- Campo de aplicación
- Herramientas de desarrollo
- Documentación disponible
- Base de usuarios
- Imposición del cliente