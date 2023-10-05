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
<p><small> IES Luis Vélez de Guevara - Spain </small></p>


## Elaboración de diagramas de clases

[![cc-by-sa](http://jamj2000.github.io/entornosdesarrollo/cc-by-sa.png)](http://creativecommons.org/licenses/by-sa/4.0/)


## Índice
--- 
- ### Introducción
- ### UML
- ### **Diagramas de clases**
- ### Diagramas de paquetes
- ### Diagramas de componentes
- ### Diagramas de despliegue
- ### Software
<!--- Note: Nota a pie de página. -->



## Introducción

En esta Unidad aprenderemos a:

- Identificar las herramientas para la elaboración de diagramas de clases.
- Interpretar el significado de diagramas de clases.
- Generar código a partir de un diagrama de clases.
- Generar un diagrama de clases mediante ingeniería inversa.



## UML

**Lenguaje de modelado unificado**

- Es un lenguaje visual de propósito general para representar **modelos**.
- Pretende proporcionar una forma estándar de representar el diseño de un sistema.
- Dispone de numerosos tipos de diagramas.
- Cada tipo de diagrama muestra un aspecto diferente del modelo.
- Actualmente disponible la versión 2.5. Existen algunas diferencias respecto a las versiones 1.x.


###  UML: Tipos de diagramas (I)

- **diagramas de estructura** (aspecto estático)
- **diagramas de comportamiento** (aspecto dinámico)


### UML: Tipos de diagramas (II)

![Tipos de diagramas](assets/uml-diagrams.png)


### UML: Diagramas de estructura

Los más utilizados son:

- **Diagramas de clases**
- Diagramas de paquetes
- Diagramas de componentes
- Diagramas de implementación



## Diagramas de clases


### Elementos

- **Clases**
- **Relaciones**
  - Nombre
  - Multiplicidad
  - Roles


### Clases

![Clase](assets/class-no-compartments.png)

![Clase con compartimentos](assets/class-compartments-impl.png)


### Interfaces

![Interface](assets/class-interface.png)

![Interface con compartimentos](assets/class-interface-compartments.png)

- **`<<estereotipo>>`**: los estereotipos permiten tomar elementos propios del UML y convertirlos en otros que se ajusten a las necesidades. Se usan cuando no existe tal elemento en UML. 


### Objetos

- No aparecen en los diagramas de clases.
- Aparecen en los diagramas de objetos y en diagramas de comportamiento.

![Objeto anónimo](assets/object-anonymous.png)

![Objeto](assets/object-named-slots-value.png)


### Relaciones

TIPOS DE RELACIONES

- **Asociación**
    - **Agregación**
    - **Composición**
- **Dependencia**
- **Generalización / Especialización**
- **Realización**


#### Asociación (I)

- Es el vínculo (conector) entre 2 clases que necesitan comunicarse entre sí.
- Se puede representar mediante una línea con una flecha que indica la dirección de navegación.
- En el caso de que la flecha esté en ambos lados, la asociación tiene asociación bidireccional. 


#### Asociación (II)

![Asociación](assets/association.png)

![Instancia de asociación](assets/link.png)

![Nota](assets/core-comment-note.png)

- Es posible agregar **notas**: hoja con la esquina superior derecha doblada.


#### Agregación

- La clase "padre" es contenedor no exclusivo de la clase "hija".
- **Si eliminamos la instancia de la clase "padre" NO se elimina la instancia de la clase "hija"**.

![Agregación](assets/agregacion.png)

Note: Aquí los términos "padre" e "hija" no tienen ninguna relación con la herencia.


#### Composición

- La clase "padre" es contenedor exclusivo de la clase "hija".
- **Si eliminamos la instancia de la clase "padre" SÍ se elimina la instancia de la clase "hija"**.

![Composición](assets/composicion.png)

Note: Aquí los términos "padre" e "hija" no tienen ninguna relación con la herencia.


#### Dependencia

![Dependencia de instanciación](assets/instantiate.png)

![Dependencia de uso de clase](assets/class-dependency-usage.png)

![Dependencia de uso de paquete](assets/use-package.png)


#### Generalización / Especialización

**HERENCIA**

![Generalización separada](assets/class-generalizaion-separate.png)

![Generalización compartida](assets/class-generalizaion-shared.png)


#### Realización

**IMPLEMENTACIÓN DE INTERFACES**

![Realización](assets/class-interface-realization.png)

![Realización bola](assets/class-interface-realization-ball.png)


#### Resumen de relaciones

![Relaciones UML](assets/relaciones-uml.png)


### Ejemplos

![Diagrama introductorio](assets/class-diagram-domain-overview.png)


#### Karts

![Karts](https://raw.githubusercontent.com/iesvelez-daw/karts/master/img/kartsUML.png)


#### Videojuego

![Videojuego](https://raw.githubusercontent.com/iesvelez-daw/videojuego/master/img/videojuegoUML.png)


#### Colegio

![Colegio](https://raw.githubusercontent.com/iesvelez-daw/colegio/master/img/colegioUML.png)


#### Zoo

![Zoo](https://raw.githubusercontent.com/iesvelez-daw/zoo/master/img/zooUML.png)



## Diagramas de paquetes

- Un **paquete** es **un espacio de nombres** que se usa **para agrupar elementos** que están relacionados semánticamente.

- **Si se elimina un paquete, también los elementos** que pertenecen al paquete. 

- **Un paquete a su vez se puede empaquetar**, por lo que cualquier paquete también podría ser miembro de otros paquetes.

![Paquete](assets/package.png)


### Ejemplo

![Diagrama de paquetes](assets/package-diagram-elements.png)



## Diagramas de componentes

- Un **componente** es una clase que representa una **parte modular de un sistema**.

![Componente 1](assets/component-1.png)

![Componente 2](assets/component-2.png)


### Interfaces

- Un componente tiene su comportamiento definido en términos de las **interfaces proporcionadas** y las **interfaces requeridas** (potencialmente expuestas a través de **puertos**).

![Interface proporcionada](assets/component-provided-interface.png)

![Interface requerida](assets/component-required-interface.png)


### Ejemplo

![Diagrama de componentes](assets/component-diagram-overview.png)



## Diagramas de despliegue (deployment)

- Muestra la arquitectura del sistema como despliegue (distribución) de **artefactos de software** a destinos de despliegue (**nodos**).


### Artefactos

- Los **artefactos** representan **elementos concretos en el mundo físico** que son el resultado de un proceso de desarrollo. 

- Ejemplos de artefactos son **archivos ejecutables**, **bibliotecas**, **archivos**, **esquemas de base de datos**, **archivos de configuración**, etc.


### Ejemplos de artefactos

![Artefactos](assets/artefacts.png)

También pueden usarse iconos personalizados.

![Artefacto - icono personalizado](assets/deployment-artifact-custom.png)


### Nodos (I)

- El **destino de la implementación** suele estar representado por un **nodo** que es un **dispositivo de hardware** o algún **entorno de ejecución de software**. 

![Nodo](assets/deployment-node.png)


### Nodos (II)

- **Un nodo puede contener en su interior otros nodos**

![Nodo compuesto](assets/deployment-node-composition-nested.png)


### Nodos (III)

- Los **nodos pueden conectarse a través de vías de comunicación** para crear sistemas en red de complejidad arbitraria.

![Comunicación entre nodos](assets/deployment-communication-protocol.png)


### Ejemplos de nodos

![Nodos 1](assets/nodes-1.png)

También pueden usarse iconos personalizados.

![Nodos - iconos personalizados](assets/nodes-2.png)


### Manifiestación de componentes

- En UML 2.x, los artefactos se implementan en los nodos, y **los artefactos podrían manifestar (implementar) componentes**. Los componentes se implementan en los nodos indirectamente a través de artefactos.

![Manifestación](assets/manifestation.png)


### Ejemplo

![Diagrama de implementación](assets/deployment-diagram-overview-specification.png)



## Software

- Enterprise Architect
- Visual Paradigm
- Microsoft Visio
- Dia, ArgoUML, Umbrello
- Plugins para Netbeans (**easyUML**, plantUML)
- Plugins para Eclipse (...)
- Plugins para IntellJ Idea (...)
- [Lista exhaustiva](https://en.wikipedia.org/wiki/List_of_Unified_Modeling_Language_tools)
