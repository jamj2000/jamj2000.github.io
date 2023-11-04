<!---
Ejemplos

<video class="stretch" controls><source src="http://clips.vorwaerts-gmbh.de/big_buck_bunny.mp4" type="video/mp4"></video>
<iframe width="560" height="315" src="https://www.youtube.com/embed/3RBq-WlL4cU" frameborder="0" allowfullscreen></iframe>

slide: data-background="#ff0000" 
element: class="fragment" data-fragment-index="1"
-->
## Entornos de desarrollo
---
![Entornos de desarrollo](http://jamj2000.github.io/entornosdesarrollo/entornosdesarrollo.png)


## Elaboración de diagramas de comportamiento

[![cc-by-sa](http://jamj2000.github.io/entornosdesarrollo/cc-by-sa.png)](http://creativecommons.org/licenses/by-sa/4.0/)


## Índice
--- 
- ### Introducción
- ### **Diagramas de casos de uso**
- ### **Diagramas de secuencia**
- ### Diagramas de estados
- ### Diagramas de actividades
- ### Referencias
<!--- Note: Nota a pie de página. -->



## Introducción

En esta Unidad aprenderemos a:

- Identificar los distintos tipos de **diagramas de comportamiento**.
- Reconocer el significado de los diagramas de casos de uso.
- Elaborar e interpretar diagramas de interacción sencillos.
- Interpretar y plantear diagramas de estados.
- Elaborar e interpretar el significado de diagramas de actividades.


### UML: Diagramas de comportamiento

Los más utilizados son:

- **Diagramas de casos de uso**
- **Diagramas de secuencia** 
- Diagramas de estados
- Diagramas de actividades



## Diagramas de casos de uso

- Se usan para **describir un conjunto de acciones (casos de uso)** que algunos **sistemas o sujetos** deben o pueden realizar en colaboración con uno o más usuarios externos del sistema (**actores**)


### Elementos

- **Actores**
- **Límites del sistema (sujeto)**
- **Casos de uso**
- **Relaciones**


### Actor (I)

- Un actor es un clasificador de comportamiento que **especifica un rol** desempeñado por una entidad externa, un usuario humano del sistema diseñado, algún otro sistema o hardware que usa los servicios del **sujeto**.

![Actor](assets/actor.png)

![Actor](assets/actor-bank.png)


### Actor (II)

- Todos los actores deben tener nombres de acuerdo al rol asumido.
- Ejemplos de nombres de actores (roles de usuario):

 - Cliente
 - Cliente web
 - Estudiante
 - Pasajero
 - Sistema de pago


### Límite del sistema (sujeto) (I)

- Un sujeto (a veces llamado **límite del sistema**) es un clasificador (incluyendo subsistema, componente o incluso clase) que **representa una empresa**, **sistema de software**, **sistema físico** o **dispositivo bajo análisis, diseño o consideración**, que tiene algún comportamiento y al que se aplica un conjunto de casos de uso.


### Límite del sistema (sujeto) (II)

- El sujeto se presenta mediante **un rectángulo con el nombre del sujeto**, las palabras clave asociadas y los estereotipos en la esquina superior izquierda.

- Los casos de uso aplicables al sujeto se encuentran dentro del rectángulo y los actores, fuera del límite del sistema.

![Sujeto](assets/subject.png)


### Caso de uso

- Los casos de uso permiten capturar los **requisitos** de los sistemas bajo diseño o consideración, describir la **funcionalidad** proporcionada por esos sistemas y determinar los requisitos que los sistemas plantean en su entorno.

![Caso de uso](assets/use-case.png)


### Ejemplos

![Diagrama de casos de uso](assets/use-case-diagram-elements.png)


### Ejemplo 1

![Compras on-line](assets/use-case-example-online-shopping.png)


### Ejemplo 1 (continuación)

![Compras on-line - checkout](assets/use-case-example-online-shopping-checkout.png)


### Ejemplo 2

![Estado final](assets/use-case-example-hospital-reception.png)



## Diagramas de secuencia

- Es el tipo más común de **diagrama de interacción**, que se centra en el intercambio de mensajes entre **varias líneas de vida**.

- El diagrama de secuencia describe una interacción al enfocarse en la **secuencia de mensajes** que se intercambian, junto con sus correspondientes especificaciones de ocurrencia en las líneas de vida.


### Elementos

- **Objetos, actores, ...**
- **Líneas de vida**
- **Mensajes**
- **Ocurrencias de ejecución**
- **Ocurrencias de destrucción**


### Línea de vida

- Es una línea discontinua que sale del objeto y avanza en el tiempo desde arriba hacia abajo.

![Línea de vida](assets/lifeline.png)


### Mensaje

- El mensaje es un elemento con nombre que define un tipo específico de comunicación entre líneas de vida de una interacción.
- El mensaje especifica no solo el tipo de comunicación, sino también el remitente y el receptor.
- Existen distintos tipos de mensajes.

![Mensaje](assets/message.png)


### Ocurrencia de ejecución

- Perido de tiempo durante el cual un objeto está en ejecución.

![Ocurrencia de ejecución](assets/execution.png)


## Ocurrencia de destrucción

- Momento en el cual un objeto es destruido.

![Ocurrencia de destrucción](assets/destruction.png)


### Ejemplos

![Diagrama de secuencia](assets/sequence-diagram-overview.png)


### Ejemplo 1

![Compras on-line](assets/sequence-examples-online-bookshop.png)


### Ejemplo 2

![Autenticación en Facebook](assets/sequence-example-facebook-authentication.png)



## Diagramas de estados

- Muestra el comportamiento discreto de una parte del sistema diseñado a través de **transiciones** de estado finito. 

- A lo largo del proceso, el sistema va pasando por varios **estados**.


### Elementos

- **Estados**
- **Transiciones**


#### Pseudoestado inicial

![Pseudoestado inicial](assets/pseudostate-initial.png)


#### Estado final

![Estado final](assets/state-final.png)


### Estados simples

![Estado simple](assets/state-simple.png)

![Estado simple con actividades internas](assets/state-simple-internal-activities.png)


### Estados compuestos

![Estado compuesto](assets/state-composite.png)

![Estado compuesto con interior oculto](assets/state-composite-hidden-decomposition.png)


### Ejemplo 1

![Ciclo del agua](assets/state-machine-example-water.png)


### Ejemplo 2

![Estados de un hilo en Java](assets/state-machine-example-java-6-thread-states.png)



## Diagramas de actividades

- Muestra el **flujo de control** o el flujo de objetos con énfasis en la secuencia y las condiciones del flujo.


### Elementos

- **Actividades**
- **Nodos**
  - **Nodo inicial**
  - **Nodo final**
  - **Nodo de decisión**
  - **Nodo de fusión**
  - **Nodo de bifurcación**
  - **Nodo de unión**


### Actividad

- La actividad es un comportamiento parametrizado representado como **flujo coordinado de acciones**.

- Una **acción** es un elemento con nombre que representa un solo paso atómico dentro de la actividad, es decir, que no se descompone más dentro de la actividad.

![Actividad](assets/activity.png)


### Ejemplos

![Diagrama de actividades](assets/control-nodes-overview.png)


### Ejemplo 1

![Compras on-line](assets/activity-examples-online-shopping.png)


### Ejemplo 2

![Proceso de pedido](assets/activity-examples-process-order.png)


### Ejemplo 3

**Uso de particiones**

![Gestión de documentos](assets/activity-example-document-management.png)



## Referencias

- [Diagramas UML de ejemplo](https://uml-diagrams.org)
- [OMG.org, donde bajar las especificaciones de UML](https://www.omg.org/spec/UML/)
- [UML.org](http://uml.org)
