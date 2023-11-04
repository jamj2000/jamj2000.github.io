<!---
Ejemplos de inserción de videos

<video class="stretch" controls><source src="http://clips.vorwaerts-gmbh.de/big_buck_bunny.mp4" type="video/mp4"></video>
<iframe width="560" height="315" src="https://www.youtube.com/embed/3RBq-WlL4cU" frameborder="0" allowfullscreen></iframe>

slide: data-background="#ff0000" 
element: class="fragment" data-fragment-index="1"

-->

## Entornos de desarrollo
---
![Entornos de desarrollo](http://jamj2000.github.io/entornosdesarrollo/entornosdesarrollo.png)


## Elementos del desarrollo de software

[![cc-by-sa](http://jamj2000.github.io/entornosdesarrollo/cc-by-sa.png)](http://creativecommons.org/licenses/by-sa/4.0/)


## Índice
--- 
- ### Introducción
- ### Conceptos básicos
- ### Ciclo de vida del software
- ### Modelos de desarrollo
- ### Lenguajes de programación

<!--- Note: Nota a pie de página. -->



## Introducción


### En esta Unidad aprenderemos a

- Reconocer la relación de los programas con los componentes del sistema informático.
- Diferenciar código fuente, objeto y ejecutable.
- Identificar las fases de desarrollo de una aplicación informática.
- Diferenciar los distintos modelos de desarrollo.
- Clasificar los lenguajes de programación.



## Conceptos básicos


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



## Ciclo de vida del software


### Ingeniería de software

> Disciplina que estudia los principios y metodologías para el desarrollo y mantenimiento de sistemas software.

- Algunos autores consideran que "___desarrollo de software___" es un término más apropiado que "___ingeniería de software___" puesto que este último implica niveles de rigor y prueba de procesos que no son apropiados para todo tipo de desarrollo de software.
- [Ingeniería del software](https://es.wikipedia.org/wiki/Ingenier%C3%ADa_de_software)


### Desarrollo de software 
#### ___Fases principales___

- __ANÁLISIS__  
- __DISEÑO__
- __CODIFICACIÓN__
- __PRUEBAS__
- __MANTENIMIENTO__  


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

- Se descompone y organiza el sistema en elementos componentes que pueden ser desarrollados por separado.
- Se especifica la interrelación y funcionalidad de los elementos componentes.
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

- Durante la explotación del sistema software es necesario realizar cambios ocasionales.
- Para ello hay que rehacer parte del trabajo realizado en las fases previas.
- Tipos de mantenimiento:
  - __Correctivo__: se corrigen defectos.
  - __Perfectivo__: se mejora la funcionalidad.
  - __Evolutivo__: se añade funcionalidades nuevas.
  - __Adaptativo__: se adapta a nuevos entornos.


###  Resultado tras cada fase (I)

- Ingeniería de sistemas: __Especificación del sistema__
- ANÁLISIS: __Especificación de requisitos del software__
- DISENO arquitectónico: __Documento de arquitectura del software__
- DISENO detallado: __Especificación de módulos y funciones__
- CODIFICACIÓN: __Código fuente__


###  Resultado tras cada fase (II)

( _Continuación_ )

- PRUEBAS de unidades: __Módulos utilizables__
- PRUEBAS de integración: __Sistema utilizable__
- PRUEBAS del sistema: __Sistema aceptado__
- Documentación: __Documentación técnica y de usuario__ 
- MANTENIMIENTO: __Informes de errores y control de cambios__



## Modelos de desarrollo


### Modelos de desarrollo de software

- Modelos clásicos (predictivos)
  - Modelo en cascada
  - Modelo en V
- Modelo de construcción de prototipos
- Modelos evolutivos o incrementales
  - Modelo en espiral (iterativos)
  - Metodologías ágiles (adaptativos)


### Modelo en cascada (I)

![Modelo en cascada](assets/cascada.png)


### Modelo en cascada (II)

- Modelo de mayor antigüedad.
- Identifica las fases principales del desarrollo software.
- Las fases han de realizarse en el orden indicado.
- El resultado de una fase es la entrada de la siguiente fase.
- Es un modelo bastante rígido que se adapta mal al cambio continuo de especificaciones.
- Existen diferentes variantes con mayor o menor cantidad de actividades.


### Modelo en V (I)

![Modelo en V](assets/v.png)


### Modelo en V (II)

- Modelo muy parecido al modelo en cascada.
- Visión jerarquizada con distintos niveles.
- Los niveles superiores indican mayor abstracción.
- Los niveles inferiores indican mayor nivel de detalle.
- El resultado de una fase es la entrada de la siguiente fase.
- Existen diferentes variantes con mayor o menor cantidad de actividades.


### Prototipos (I)

- A menudo los requisitos no están especificados claramente:
  - por no existir experiencia previa.
  - por omisión o falta de concreción del usuario/cliente.

![Modelo de construcción de prototipos](assets/prototipos.png)


### Prototipos (II)

- Proceso:
  - Se crea un prototipo durante la __fase de análisis__ y es probado por el usuario/cliente para refinar los requisitos del software a desarrollar.
  - Se repite el paso anterior las veces necesarias.


### Prototipos (III)

- Tipos de prototipos:
  - __Prototipos rápidos__ 
    - El prototipo puede estar desarrollado usando otro lenguaje y/o herramientas.
    - Finalmente el prototipo se desecha.
  - __Prototipos evolutivos__ 
    - El prototipo está diseñado en el mismo lenguaje y herramientas del proyecto.
    - El prototipo se usa como base para desarrollar el proyecto.


### Modelo en espiral (I)

- Desarrollado por Boehm en 1988.
- La actividad de ___ingeniería___ corresponde a las fases de los modelos clásicos: análisis, diseño, codificación, ...

![Modelo en espiral](assets/espiral.png)


### Modelo en espiral (II)
#### ___Aplicado a la programación orientada a objetos___

- En la actividad de ___ingeniería___ se da gran importancia a la reutilización de código.

![Modelo en espiral](assets/espiral-poo.png)


### Metodologías ágiles (I)

- Son métodos de ingeniería del software basados en el desarrollo iterativo e incremental.
- Los requisitos y soluciones evolucionan con el tiempo según la necesidad del proyecto.
- El trabajo es realizado mediante la colaboración de equipos auto-organizados y multidisciplinarios, inmersos en un proceso compartido de toma de decisiones a corto plazo.
- Las metodologías más conocidas son:
  - Kanban
  - Scrum
  - XP (eXtreme Programming)


### Metodologías ágiles (II)

[Manifiesto por el Desarrollo Ágil](https://es.wikipedia.org/wiki/Manifiesto_%C3%A1gil)

- __Individuos e interacciones__ sobre procesos y herramientas
- __Software funcionando__ sobre documentación extensiva
- __Colaboración con el cliente__ sobre negociación contractual
- __Respuesta ante el cambio__ sobre seguir un plan


#### __Kanban (I)__

- También se denomina "sistema de tarjetas".
- __Desarrollado inicialmente por Toyota para la industria de fabricación de productos__.
- __Controla por demanda__ la fabricación de los productos necesarios en la cantidad y tiempo necesarios.
- Enfocado a entregar el máximo valor para los clientes, utilizando los recursos justos.
- [Lean manufacturing](https://es.wikipedia.org/wiki/Lean_manufacturing)
- [Kanban en desarrollo software](https://dosideas.com/noticias/metodologias/184-como-usar-kanban-en-el-desarrollo-de-software)


#### __Kanban (II)__

Pizarra kanban

![Pizarra kanban](assets/kanban-board.png)


#### __Scrum: Conceptos__

- Modelo de desarrollo incremental.
- Iteraciones (__sprint__) **regulares** cada 2, 3 o 4 semanas.
- Al principio de cada iteración se establecen sus __objetivos priorizados__ (__sprint backlog__).
- Al finalizar cada iteración se obtiene una __entrega parcial utilizable por el cliente__.
- Existen reuniones diarias para tratar la marcha del _sprint_.


#### __Scrum: Proceso__

![Proceso SCRUM](assets/scrum.png)


#### __Scrum: Roles principales__

**Product Owner**
Es "la voz del cliente". Define criterios de aceptación y asegura de que se cumplan.

**Scrum Master**
Asegura que se sigue la metodología Scrum. Motiva y facilita el trabajo del equipo. 

**Team**
Equipo de desarrollo auto-organizado y multifuncional. Entre 6 y 10 miembros.


#### __Scrum: Artefactos__

**Product Backlog**
Lista ordenada con los requisitos del producto

**Sprint Backlog**
Lista de requisitos sacados del backlog para su desarrollo durante el sprint

**Incremento**
Estado del producto después de cada sprint


#### __Scrum: Eventos__

**Sprint**
Evento principal, que contiene al resto de eventos. Duracción máxima: 1 mes.

**Sprint Planning**
Reunión inicial donde se planifica el trabajo del Sprint. Duración máxima: 8 horas.

**Daily Scrum**
Reunión diaria de puesta en común sobre la marcha del sprint. Duración máxima: 15 minutos.

**Scrum Review**
Reunión final para evaluar el incremento obtenido. Duración máxima: 4 horas.

**Scrum Retrospective**
Reunión final para evaluar la correcta aplicación de la metodología Scrum. Duración máxima: 3 horas.


#### __XP (Programación eXtrema): Valores__

- Simplicidad
- Comunicación
- Retroalimentación
- Valentía o coraje
- Respeto o humildad 

https://es.wikipedia.org/wiki/Programaci%C3%B3n_extrema


#### __XP (Programación eXtrema): Características__

- Diseño sencillo
- Pequeñas mejoras continuas
- Pruebas y refactorización
- Integración continua
- __Programación por parejas__
- __El cliente se integra en el equipo de desarrollo__
- Propiedad del código compartida
- Estándares de codificación
- 40 horas semanales

https://es.wikipedia.org/wiki/Programaci%C3%B3n_extrema



## Lenguajes de programación


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


### Historia

![Historia simplificada](assets/simple-lang-tree.png)

[**Historia completa**](https://www.levenez.com/lang/lang.pdf)


### Criterios para la selección de un lenguaje

- Campo de aplicación
- Experiencia previa
- Herramientas de desarrollo
- Documentación disponible
- Base de usuarios
- Reusabilidad
- Portabilidad
- Imposición del cliente

