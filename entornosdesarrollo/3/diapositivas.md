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


## Diseño y realización de pruebas

[![cc-by-sa](assets/cc-by-sa.png)](http://creativecommons.org/licenses/by-sa/4.0/)


## Índice
--- 
### Introducción
### Pruebas
### Integración
### Calidad

<!--- Note: Nota a pie de página. -->



## Introducción


En esta Unidad aprenderemos a:

- Identificar los diferentes tipos de pruebas.
- Definir casos de prueba.
- Efectuar pruebas unitarias de clases y funciones.
- Efectuar pruebas de integración, de sistema y de aceptación.
- Realizar medidas de calidad sobre el software desarrollado.


### Framework

En general, un framework (marco de trabajo) está compuesto por:

- un conjunto de las mejores prácticas y suposiciones
- herramientas comunes
- bibliotecas 

Permite unificar el proceso de desarrollo entre desarrolladores.



## Pruebas


### Forma de las pruebas

#### Pruebas dinámicas
Requieren la ejecución de la aplicación. Permiten medir el comportamiento de la aplicación desarrollada.

#### Pruebas estáticas
Se realizan sin ejecutar el código de la aplicación. Se examina el código fuente.


### Estrategias de prueba

#### Caja negra
Se estudia el sistema desde fuera.

#### Caja blanca
Se examina el código fuente y su ejecución.


### Estrategias de prueba de caja negra

- Se estudia el sistema desde fuera.
- Se trabaja sobre la interfaz.
- No se tienen en cuenta los detalles internos de funcionamiento.
- Se proporcionan entradas y se estudian las salidas.
- Principales técnicas:
  - Particiones de equivalencia
  - Valores límite


### Estrategias de prueba de caja blanca

- Se examina el código fuente y su ejecución.
- Se comprueban los flujos de ejecución dentro de cada unidad (función, clase, módulo, etc.) 
- También pueden comprobarse los flujos entre unidades durante la integración.
- E incluso entre subsistemas, durante las pruebas de sistema.
- Principales técnicas:
  - Cubrimiento lógico
  - Prueba de bucles


### Tipos de pruebas

#### Funcionales
Evaluan el cumplimiento de los requisitos.

#### No funcionales
Evaluan aspectos adicionales como rendimiento, seguridad, ... 


### Pruebas funcionales

- Pruebas unitarias (o de unidad)
- Pruebas de integración 
- Pruebas del sistema
- Pruebas de humo (smooke test)
- Pruebas alfa y beta
- Pruebas de aceptación (validación por parte del cliente)
- Pruebas de regresión


### Pruebas no funcionales

- Pruebas de usabilidad
- Pruebas de rendimiento
- Pruebas de stress
- Pruebas de seguridad
- Pruebas de compatibilidad
- Pruebas de portabilidad
- ...


### TDD

- Desarrollo guiado por pruebas de software, o Test-Driven Development (TDD) 
  - Escribir las pruebas primero (Test First Development).
  - Refactorización (Refactoring).


### Mecanismos de prueba

- Manual
  - Mediante pruebas realizadas por personal de la empresa o externo.
- Automático
  - Mediante software que ejecuta código de forma automatizada y compara los resultados obtenidos y los resultados esperados.


###__Soporte del depurador__

- Puntos de ruptura
- Ejecución paso a paso
- Análisis de variables


### Automatización de pruebas

- Frameworks de pruebas (xUnit)
- Aserciones

https://en.wikipedia.org/wiki/XUnit


### Frameworks para pruebas

- Java: JUnit, TestNG
- C++: CppUnit, Google Test
- PHP: PHPUnit
- Javascript: Mocha

https://en.wikipedia.org/wiki/List_of_unit_testing_frameworks


### Caso de prueba

- Una entrada conocida (precondición) --> Una salida esperada (postcondición)

http://www.jtech.ua.es/j2ee/publico/lja-2012-13/sesion04-apuntes.html


### JUnit - Anotaciones

- @BeforeClass
- @Before
- @Test
- @After
- @AfterClass


### JUnit - Aserciones

```java
import org.junit.Test;
import static org.junit.Assert.*;

... 
assertTrue(expresión)	comprueba que expresión evalúe a true
assertFalse(expresión)	comprueba que expresión evalúe a false
assertEquals(esperado,real)	comprueba que esperado sea igual a real
assertNull(objeto)	comprueba que objeto sea null
assertNotNull(objeto)	comprueba que objeto no sea null
assertSame(objeto_esperado,objeto_real)	comprueba que objeto_esperado y objeto_real sean el mismo objeto
assertNotSame(objeto_esperado,objeto_real)	comprueba que objeto_esperado no sea el mismo objeto que objeto_real
fail()	hace que el test termine con fallo

```
http://junit.org/junit4/javadoc/4.12/org/junit/Assert.html



## Integración


### Formas de integración

- Integración Big bang
- Integración Descendente
- Integración Ascendente
- Integración Continua (CI)


### Servidores de integración continua

> CI : Integración continua  
> CD : Despliegue continuo

- Jenkins
- Bamboo
- TravisCI
- CircleCI

Note: CI=Continuous Integration / CD=Continuous Delivery.

# Calidad


## Factores de calidad

- Corrección
- Fiabilidad
- Eficiencia
- Seguridad
- Facilidad de uso
- Mantenibilidad
- Flexibilidad
- Facilidad de prueba
- Transportabilidad
- Reusabilidad
- Interoperatividad


## Calidad del proceso/producto (QA/QC)

- QA es un conjunto de actividades para garantizar la __calidad en los procesos__ mediante los cuales se desarrollan los productos. 
- QC es un conjunto de actividades para garantizar __la calidad de los productos__. Las actividades se centran en identificar defectos en los productos reales producidos.

> control de calidad = medición de la calidad de un producto -> Pruebas

Note: QA = Quality Assurance / QC = Quality Control
