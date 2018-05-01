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


## Elaboración de diagramas de clases

[![cc-by-sa](assets/cc-by-sa.png)](http://creativecommons.org/licenses/by-sa/4.0/)


## Índice
--- 
### Introducción
### UML: Lenguaje de modelado unificado
### UML: Software para crear diagramas
### UML: Tipos de diagramas
### UML: Diagramas de clases


<!--- Note: Nota a pie de página. -->



## Introducción

En esta Unidad aprenderemos a:

- Identificar los conceptos básicos de la programación orientada a objetos.
- Instalar el módulo del entorno integrado de desarrollo que permite la utilización de diagramas de clases.
- Identificar las herramientas para la elaboración de diagramas de clases.
- Interpretar el significado de diagramas de clases.
- Trazar diagramas de clases a partir de las especificaciones de las mismas.
- Generar código a partir de un diagrama de clases.
- Generar un diagrama de clases mediante ingeniería inversa.



## UML: Lenguaje de modelado unificado

- Es un lenguaje visual de propósito general para representar **modelos**.
- Pretende proporcionar una forma estándar de representar el diseño de un sistema.
- Dispone de numerosos tipos de diagramas.
- Cada tipo de diagrama muestra un aspecto diferente del modelo.



## UML: Software para crear diagramas

- Enterprise Architect
- Visual Paradigm
- Microsoft Visio
- Dia, ArgoUML, Umbrello
- Plugins para Netbeans (**easyUML**, plantUML)
- Plugins para Eclipse (...)
- Plugins para IntellJ Idea (...)
- [Lista exhaustiva](https://en.wikipedia.org/wiki/List_of_Unified_Modeling_Language_tools)



## UML: Tipos de diagramas

- **diagramas de estructura** (aspecto estático)
- **diagramas de comportamiento** (aspecto dinámico)

![Tipos de diagramas](assets/uml-diagrams.png)



## UML: Diagramas de clases

![Diagrama introductorio](assets/class-diagram-domain-overview.png)


### Clases

![Clase](assets/class-no-compartments.png)

![Clase con compartimentos](assets/class-compartments-impl.png)


### Objetos

![Objeto](assets/object-named-slots-value.png)


### Interfaces

![Interface](assets/class-interface.png)

![Interface con compartimentos](assets/class-interface-compartments.png)


### Relaciones

- Asociación
    - Agregación
    - Composición
- Dependencia
- Generalización
- Realización


#### Asociación

![Asociación](assets/association.png)

![Instancia de asociación](assets/link.png)

![Nota](assets/core-comment-note.png)


#### Agregación

![Agregación](assets/shared-aggregation.png)


#### Composición

![Composición](assets/class-composition.png)

![Composición opcional](assets/class-composition-optional.png)


#### Dependencia

![Dependencia de instanciación](assets/instantiate.png)

![Dependencia de uso de clase](assets/class-dependency-usage.png)

![Dependencia de uso de paquete](assets/use-package.png)


#### Generalización (herencia)

![Generalización separada](assets/class-generalizaion-separate.png)

![Generalización compartida](assets/class-generalizaion-shared.png)


#### Realización (implementación de interfaces)

![Realización bola](assets/class-interface-realization-ball.png)

![Realización](assets/class-interface-realization.png)


### Ejemplos

- [Karts](https://raw.githubusercontent.com/iesvelez-daw/karts/master/img/kartsUML.png)
- [Videojuego](https://raw.githubusercontent.com/iesvelez-daw/videojuego/master/img/videojuegoUML.png)
- [Colegio](https://raw.githubusercontent.com/iesvelez-daw/colegio/master/img/colegioUML.png)
- [Zoo](https://raw.githubusercontent.com/iesvelez-daw/zoo/master/img/zooUML.png)




