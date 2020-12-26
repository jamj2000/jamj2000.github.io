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
<p><small> IES Luis Vélez de Guevara - Écija - Spain </small></p>


## Diseño y realización de pruebas

[![cc-by-sa](http://jamj2000.github.io/entornosdesarrollo/cc-by-sa.png)](http://creativecommons.org/licenses/by-sa/4.0/)


## Índice
--- 
- ### Introducción
- ### Pruebas
- ### Integración
- ### Calidad

<!--- Note: Nota a pie de página. -->



## Introducción


En esta Unidad aprenderemos a:

- Identificar los diferentes tipos de pruebas.
- Definir casos de prueba.
- Efectuar pruebas unitarias de clases y funciones.
- Efectuar pruebas de integración, de sistema y de aceptación.
- Realizar medidas de calidad sobre el software desarrollado.


### Objetivos de las pruebas

- Una buena prueba debe centrarse en dos objetivos: 

 1. probar si el software no hace lo que debe hacer
 2. probar si el software hace lo que no debe hacer.

- Existen distintos **frameworks** para la realización de pruebas.


### Framework

- En general, un framework (marco de trabajo) está compuesto por:

  - un conjunto de las mejores prácticas y suposiciones
  - herramientas comunes
  - bibliotecas 

- Permite unificar el proceso de desarrollo entre desarrolladores.



## Pruebas


### Forma de las pruebas

- __Pruebas dinámicas:__
Requieren la ejecución de la aplicación. Permiten medir el comportamiento de la aplicación desarrollada.

- __Pruebas estáticas:__
Se realizan sin ejecutar el código de la aplicación. Se examina el código fuente.


### Estrategias de prueba

- __Caja negra:__
Se estudia el sistema desde fuera. Son pruebas de funcionalidad.

- __Caja blanca:__
Se examina el código fuente y su ejecución. Son pruebas estructurales.


### Estrategias de prueba

![Caja blanca vs Caja negra](assets/caja_blanca-caja_negra.png)


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
  - Cobertura de código
  - Prueba de bucles


### Tipos de pruebas

- __Funcionales:__
Evaluan el cumplimiento de los requisitos.

- __No funcionales:__
Evaluan aspectos adicionales como rendimiento, seguridad, ... 


### Pruebas funcionales

- Pruebas unitarias (o de unidad)
- Pruebas de regresión
- Pruebas de integración 
- Pruebas del sistema
- Pruebas de humo (smoke test)
- Pruebas alfa y beta
- Pruebas de aceptación (validación por parte del cliente)


### Pruebas no funcionales

- Pruebas de usabilidad
- Pruebas de rendimiento
- Pruebas de stress
- Pruebas de seguridad
- Pruebas de compatibilidad
- Pruebas de portabilidad
- ...


### Mecanismos de prueba

- Manual
  - Mediante pruebas realizadas por personal de la empresa o externo.
- Automático
  - Mediante software que ejecuta código de forma automatizada y compara los resultados obtenidos y los resultados esperados.


### Soporte del depurador

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

- Un caso de prueba se compone de:
  - Una entrada conocida  --> Una salida esperada 

- Por ejemplo:
  - suma (2,3)  -->  5
  - resta(2,3)  --> -1

http://www.jtech.ua.es/j2ee/publico/lja-2012-13/sesion04-apuntes.html


### JUnit4/5 - Anotaciones I

Las anotaciones JUnit se anteponen a la definición del método de prueba. Son:

JUnit 4          | JUnit 5
-----------------|----------------------
@BeforeClass     | @BeforeAll
@Before          | @BeforeEach
@Test            | @Test
@After           | @AfterEach
@AfterClass      | @AfterAll
@Ignore          | @Ignore


### JUnit4 - Anotaciones II

- **@BeforeClass**: el método es invocado antes de iniciar todos los tests. Sólo puede haber un método con esta anotación.
- **@AfterClass**: el método es invocado después de finalizar todos los tests. Sólo puede haber un método con esta anotación.
- **@Before**: Se ejecuta antes de de cada test.
- **@After**: Se ejecuta después de cada test.
- **@Ignore**: Los métodos marcados con esta anotación no serán ejecutados.
- **@Test**: Representa un test que se debe ejecutar. 


### JUnit - Aserciones

```java
import static org.junit.Assert.*;

// ... 
fail()                         // el test termina con fallo
assertTrue(expresión)          // expresión es true ?
assertFalse(expresión)         // expresión es false ?
assertEquals(esperado,real)    // esperado es igual a real ?
assertNotEquals(esperado,real) // esperado es distinto de real ?
assertNull(objeto)             // objeto es null ?
assertNotNull(objeto)          // objeto es distinto de null ?

// objeto_esperado es igual a objeto_real ?
assertSame(objeto_esperado,objeto_real)
// objeto_esperado es distinto de objeto_real ?
assertNotSame(objeto_esperado,objeto_real)
```

http://junit.org/junit4/javadoc/4.12/org/junit/Assert.html


### TDD

- Desarrollo guiado por pruebas de software, o Test-Driven Development (TDD) 
  - Escribir las pruebas primero (Test First Development).
  - Refactorización (Refactoring).



## Integración


### Formas de integración

- Integración Big bang
- Integración Descendente
- Integración Ascendente
- Integración Continua (CI)


### Servidores de integración continua

> CI : Integración continua  
> CD : Entrega continua

- Jenkins
- Bamboo
- TravisCI
- CircleCI

Note: CI=Continuous Integration / CD=Continuous Delivery.


### Servidores de integración continua

![Jenkins, Bamboo, Travis](assets/jenkins-bamboo-travisci.png)


### Cobertura del código

- Es una medida que indica el porcentaje de código que ha sido ejecutado durante las pruebas.
- Es aconsejable que sea del 100%.
- Si es del 100% entonces se ha ejecutado todo el código fuente durante las pruebas.
- Si es menor del 100% entonces existe código fuente que no se ha ejecutado durante las pruebas.
- Es posible realizar la cobertura tanto desde el IDE como desde un servicio web apropiado.



## Calidad


### Control de calidad

Medición de la calidad de un producto --> Pruebas


### Calidad del proceso/producto (QA/QC)

- QA es un conjunto de actividades para garantizar la __calidad en los procesos__ mediante los cuales se desarrollan los productos. 
- QC es un conjunto de actividades para garantizar __la calidad de los productos__. Las actividades se centran en identificar defectos en los productos reales producidos.

Note: QA = Quality Assurance / QC = Quality Control


### Factores de calidad

- Corrección
- Fiabilidad
- Eficiencia
- Seguridad
- Facilidad de uso
- Mantenibilidad
- Flexibilidad
- Facilidad de prueba
- Portabilidad
- Reusabilidad
- Interoperatividad
