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

(assets/class-diagram-domain-overview.png)


### Clases

![](assets/class-no-compartments.png)
![](assets/class-compartments-impl.png)


### Objetos

![](assets/object-named-slots-value.png)


### Interfaces

![](assets/class-interface.png)
![](assets/class-interface-compartments.png)


### Relaciones

- Asociación
    - Agregación
    - Composición
- Dependencia
- Generalización
- Realización


#### Asociación

![](assets/association.png)
![](assets/link.png)
![](assets/core-comment-note.png)


#### Agregación

![](assets/shared-aggregation.png)


#### Composición

![](assets/class-composition.png)
![](assets/class-composition-optional.png)


#### Dependencia

![](assets/instantiate.png)
![](assets/class-dependency-usage.png)
![](assets/use-package.png)


#### Generalización (herencia)

![](assets/class-generalizaion-separate.png)
![](assets/class-generalizaion-shared.png)


#### Realización (implementación de interfaces)

![](assets/class-interface-realization-ball.png)
![](assets/class-interface-realization.png)


### Ejemplos

- https://raw.githubusercontent.com/iesvelez-daw/karts/master/img/kartsUML.png
- https://raw.githubusercontent.com/iesvelez-daw/videojuego/master/img/videojuegoUML.png
- https://raw.githubusercontent.com/iesvelez-daw/colegio/master/img/colegioUML.png 
- https://raw.githubusercontent.com/iesvelez-daw/zoo/master/img/zooUML.png




