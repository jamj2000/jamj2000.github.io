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


## Optimización y documentación

[![cc-by-sa](assets/cc-by-sa.png)](http://creativecommons.org/licenses/by-sa/4.0/)


## Índice
--- 
### Introducción
### Optimización
### Documentación
### Control de versiones

<!--- Note: Nota a pie de página. -->



## Introducción


En esta Unidad aprenderemos a:

- Trabajar de forma habitual con un sistema de control de versiones.  
- Identificar los patrones de refactorización más usuales.
- Revisar el código fuente usando un analizador de código.
- Documentar el código fuente.



## Optimización


### Hediondez del código

- También llamado __code smell__ en inglés
- Es síntoma en el código fuente que indica posiblemente un problema más profundo.
- Usualmente no son bug de programación (errores): no son técnicamente incorrectos y en realidad no impiden que el programa funcione correctamente. 
- Indica deficiencias en el diseño que puede ralentizar el desarrollo o aumentan el riesgo de errores o fallos en el futuro.
- Es un motivo importante para realizar refactorización.
- [Hediondez del código](https://es.wikipedia.org/wiki/Hediondez_del_c%C3%B3digo)


### Análisis de código

- Tipos:
  - __Análisis dinámico__ (unit tests)
  - __Análisis estático__ (__lint__)


### Analizador estático (Linter)

- [Introducción a los linters -en inglés-](https://github.com/mcandre/linters)


### Ejemplos de linters

- C: lint
- Java: sonar
- Javascript: JSLint, ESLint 


### Refactorización
 
- Es el proceso de reestructurar un código fuente, alterando su estructura interna sin cambiar su comportamiento externo. 
- Técnicas:
  - Renombrado de variables
  - Pasar código duplicado a funciones
  - Eliminación de código inalcanzable
  - Eliminación de código redundante 
  - Eliminación de código muerto
  - ...

[Artículo en Wikipedia](https://es.wikipedia.org/wiki/Eliminaci%C3%B3n_de_c%C3%B3digo_muerto)


### Inspección de código

__Continuous Inspection__

- Scrutinizer
- Codecov
- SonarQube


#### Scrutinizer

[ ![scrutinizer](assets/scrutinizer.png)  ](https://scrutinizer-ci.com)

- PHP, Python y Ruby soportados
- 14 días de prueba gratis
- Precio/Mes:
  - Plan Basic: 49 €
  - Plan Professional: 99 €
  - Plan Unlimited: 199 €

Note: A fecha Diciembre 2017


#### Codecov

[ ![codecov](assets/codecov.png)  ](https://codecov.io)

- Más de 20 lenguajes soportados
- Precio/Mes:
  - Plan Free: 0 $
  - Plan Team: 2,50 $ por repositorio
  - Plan Enterprise: 20 $ por usuario

Note: A fecha Diciembre 2017


#### SonarQube

[ ![sonarqube](assets/sonarqube.png)  ](https://www.sonarqube.org/)

- Más de 20 lenguajes soportados
- Precio/Mes:
  - Plan Open Source: 0 $
  - Plan Private Projects: Desde 5 $ 

Note: A fecha Diciembre 2017



## Documentación


### Insignias (badges)

[ ![badges](assets/badges.png) ](https://shields.io/)


### Tipos de documentación

- Documentación de código
- Documentación técnica
- Documentación de usuario


### Formatos de documentación

- **HTML** (p. ej. Javadoc)
- **Markdown** (p. ej. Gitbook)
- **reStructuredText** (p. ej. Readthedocs)
- **asciiDoc** 



## Control de versiones


### Sistemas más conocidos:

  - CVS
  - Subversion
  - Mercurial
  - **Git**


### Git

**Características**

- Moderno
- Distribuido
- Eficiente


### Git (Áreas)

![Git areas](assets/git-areas1.png)


### Git (Áreas)

![Git areas](assets/git-areas2.png)


### Git (Conceptos)

- Repository (local & remote)
- Commit
- Branch
  - Checkout
  - Merge (fast-forward, 3-way)


### Git (Ramas)

![Git areas](assets/git-branches.png)


### Git (Comandos)

```bash
# Configuración
  config 

# Repositorios
  clone, remote add, remote rm

# Básicos
 init, status, log, add, rm, commit, push, pull

# Ramas (branches)
  branch, branch -d, merge, checkout, stash

# Otros
  diff, tag, submodule
```

[CheatSheet](https://services.github.com/on-demand/downloads/github-git-cheat-sheet.pdf)


### Sitios que soportan GIT

- __[GitHub](https://github.com)__
- __[Bitbucket](https://bitbucket.org/)__
- __[GitLab](https://gitlab.com/ )__
- __[Coding -en chino-](https://coding.net/)__

![Git sites](assets/git-sites.png)