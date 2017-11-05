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

<!--- Note: Nota a pie de página. -->



## Introducción


En esta Unidad aprenderemos a:

- Identificar los diferentes tipos de pruebas.
- Definir casos de prueba.
- Efectuar pruebas unitarias de clases y funciones.
- Efectuar pruebas de integración, de sistema y de aceptación.
- Realizar medidas de calidad sobre el software desarrollado.


## Pruebas


### Forma de las pruebas

- __Pruebas estáticas__
  Se realizan sin ejecutar el código de la aplicación. Se examina el código fuente.
- __Pruebas dinámicas__
  Requieren la ejecución de la aplicación. Permiten medir el comportamiento de la aplicación desarrollada.


### Mecanismos de prueba

- Manual
  - Mediante pruebas realizadas por personal de la empresa o externo.
- Automático
  - Mediante software que ejecuta código de forma automatizada y compara los resultados obtenidos y los resultados esperados.


#### Pruebas manuales (I)

__Uso del depurador__

- Puntos de ruptura
- Ejecución paso a paso
- Análisis de variables


#### Pruebas manuales (II)

__Ejecución de código__

- Prueba de condiciones
- Prueba de bucles
- Empleo de intuición


### Automatización de pruebas (I)

- 


### Estrategias de prueba (I)

- De __caja negra__
  - Se estudia el sistema desde fuera.
  - Se trabaja sobre la interfaz.
  - No se tienen en cuenta los detalles internos de funcionamiento.
  - Se proporcionan entradas y se estudian las salidas.
- De __caja blanca__
  - Se examina el código fuente y su ejecución.
  - Se comprueban los flujos de ejecución dentro de cada unidad (función, clase, módulo, etc.) 
  - También pueden comprobarse los flujos entre unidades durante la integración.
  - E incluso entre subsistemas, durante las pruebas de sistema.


### Estrategías de prueba (II)

- De __caja negra__
  - Particiones de equivalencia
  - Valores límite
  - Comparación de versiones
- De __caja blanca__
  - Cubrimiento lógico
  - Prueba de bucles
  - Empleo de intuición


### Tipos de pruebas

- Funcionales
  - Evaluan el cumplimiento de los requisitos.
- No funcionales
  - Evaluan aspectos adicionales como rendimiento, seguridad, ... 


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


#### Pruebas unitarias

- Desarrollo guiado por pruebas de software, o Test-driven development (TDD) 


#### Pruebas de integración


#### Pruebas de sistema



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
- TravisCI
- CircleCI


### Factores de calidad

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
