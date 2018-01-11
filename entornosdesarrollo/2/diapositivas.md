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


## Entornos integrados de desarrollo

[![cc-by-sa](assets/cc-by-sa.png)](http://creativecommons.org/licenses/by-sa/4.0/)


## Índice
--- 
### Introducción
### Herramientas básicas
### Entornos integrados de desarrollo (IDE)

<!--- Note: Nota a pie de página. -->



## Introducción


En esta Unidad aprenderemos a:

- Instalar entornos de desarrollo, propietarios y libres.
- Personalizar y automatizar el entorno de desarrollo.
- Generar ejecutables a partir de código fuente.
- Identificar las características comunes y específicas de diversos entornos de desarrollo.


### Conceptos

- Codigo fuente
- Codigo intermedio u objeto
- Codigo binario
- Bibliotecas (librerías)
- Compilar
- Enlazar (Link)
- Interpretar



## Herramientas básicas


### Lo básico

- Editor de texto: permite escribir código fuente
- Compilador: genera código objeto a partir del código fuente
- Enlazador: agrupa varios archivos objeto en uno binario
- Interprete: lee código fuente y genera código binario para su ejecución


### Bibliotecas (o librerías) (I)

> Conjunto de archivos objeto que extienden la funcionalidad del lenguaje

- __Biblioteca estándar__ del lenguaje
- __Bibliotecas adicionales__


### Bibliotecas (o librerías) (II)

- __Biblioteca estándar del lenguaje C__
  - Entrada y salida por terminal
  - Manejo de archivos
  - Funciones matemáticas
- __Biblioteca estándar del lenguaje Java__
  - Entrada y salida por terminal
  - Manejo de archivos
  - Funciones matemáticas
  - Interfaz gráfica 
  - Red
  - Bases de datos
  - Gráficos (sólo 2D)


### Bibliotecas (o librerías) (III)

- Cada biblioteca está compuesta por varios archivos objeto
- Tipos:
  - bibliotecas __dinámicas__ (.DLL o .so) (.jar en Java) 
  - bibliotecas __estáticas__ (.LIB o .a)


### Bibliotecas (o librerías) (IV)

- Partes de una biblioteca:
  - __Especificación__ (ofrece una __API__)
  - __Implementación__ 

Note: __API__ = Interfaz de Programación de Aplicaciones


### Entorno necesario en java

- __JRE__: necesario para ejecutar programas
  - JVM (inteprete java)
  - Biblioteca estándar
- __JDK__: necesario para desarrollar programas
  - Herramientas: javac, jar, javadoc, ...


### Construir (Build) (I) 

> __Construir (Build) = Compilar + Enlazar__

- Opciones:
 - Equipo local
 - Servidor de construcción


### Construir (Build) (II) 
#### __Equipo local__

- __Herramientas de construcción__
  - make, ninja (C, C++)
  - ant, maven, gradle (Java)
  - grunt, gulp (Javascript)
  - rake (ruby)

![ant-maven-gradle](assets/ant-maven-gradle.png)


### Construir (Build) (III) 
#### __Archivos de construcción__

- __Buildfiles__
  - make: __Makefile__
  - ninja: __build.ninja__
  - ant: __build.xml__
  - maven: __pom.xml__
  - gradle: __build.gradle__
  - grunt: __Gruntfile.js__
  - gulp: __gulpfile.js__
  - rake: __Rakefile__


### Construir (Build) (IV) 
#### __Generadores de _buildfiles_ __

- __Herramienta y archivo asociado__
  - CMake: CMakeLists.txt
  - Meson: meson.build  


### Construir (Build) (V) 
#### __Servidores de construcción__

- __Integración continua (CI)__
  - Jenkins 
  - Bamboo
  - TravisCI
  - CircleCI
  - TeamCity

![jenkins-bamboo-travisci](assets/jenkins-bamboo-travisci.png)



## Entornos integrados de desarrollo (IDE)


### Ejemplos

- Destinados principalmente a C++:
  - DevC++
  - Microsoft Visual Studio
  - QtCreator
- Destinados principalmente a Java:
  - Netbeans
  - Eclipse
  - IntelliJ IDEA
  - Oracle JDeveloper

 
