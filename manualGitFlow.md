 # GIT-FLOW

Es un modelo alternativo de creación de rama en Git en el que se utilizan ramas de función y varias ramas principales. En comparación con el desarrollo basado en troncos, Gitflow tiene diversas ramas de más duración y mayores confirmaciones. Según este modelo, los desarrolladores crean una rama de función y retrasan su fusión con la rama principal del tronco hasta que la función está completa

## Ventajas

1. **Organización clara**: Git-flow establece un conjunto definido de ramas, lo que proporciona una estructura organizativa clara para el desarrollo de software. Las ramas principales, como **`master`** y **`develop`**, tienen funciones específicas, lo que facilita el seguimiento del progreso del proyecto.

2. **Facilita el desarrollo colaborativo**: Al definir roles claros para las diferentes ramas, Git-flow facilita el trabajo colaborativo entre desarrolladores. Cada función tiene su propio espacio de trabajo, lo que minimiza las interferencias y conflictos entre los cambios de código

3. **Control de calidad**: El modelo proporciona un flujo estructurado para la implementación de características, corrección de errores y lanzamiento de versiones, lo que facilita el control de calidad y la garantía de estabilidad del software.

## Necesidades

1. **Estructura organizativa clara:** Proyectos que requieren una estructura clara y definida para el desarrollo y la gestión del ciclo de vida del software pueden beneficiarse enormemente de Git-flow.
2. **Desarrollo colaborativo**: Equipos de desarrollo con varios miembros que trabajan en diferentes características simultáneamente necesitan un marco que facilite la colaboración sin generar conflictos constantes en el código.
3. **Control de versiones robusto**: Proyectos que necesitan un control de versiones robusto, especialmente aquellos con múltiples versiones lanzadas y en desarrollo simultáneo, pueden encontrar en Git-flow una solución efectiva para gestionar este aspecto.

## Motivos

1. **Estándar de la industria:** Git-flow se ha convertido en un estándar de la industria para muchos equipos de desarrollo gracias a su claridad y eficacia. 
2. **Compatibilidad con herramientas :** es compatible con varias herramientas de control de versiones y sistemas de integración continúa.

## Workflow alternativo a git-flow
Existen workflows alternativos a glitflow, algunos de ellos son:
### Github Flow
>La principal diferencia es que  en esta se elimina la rama develop.Sus principios son:
-Todo lo que haya en la **rama master debe ser desplegado.**
-Para las nuevas caracteristicas se crea una rama Master
-Hacer commit en la rama local y push en el server
-Usar el **pull Request** para conseguir feedback
-Una vez comprobado el código se puede mergear con el master y luego de mergearlo hay que desplegar los cambios
### GitLab Flow
>Este nace de las carencias de los dos anteriores. El problema que busca resolver es cuando no es posible que todo el contenido del master sea desplegado.
### Trunk-based Flow
>Parecido a GitHub-flow. la principal diferencia es una nueva característica (releases branch) y un cambio de filosofia:
-Los developers trabajan sobre el master
-No se puede crear features branch utilizando documentación técnica.
-Intentar usar la metodología **Pair-Programming**

### Master-only Flow
>Es solo una rama infinita, no hay ramas todos se hace sobre el master
## Funcionamiento de git-flow

### Como se organizan las ramas
Se trabaja sobre dos ramas main(`main`,`develop`),estas han de estar debidamente etiquetadas con el nombre de versión.
>#### Main 
>Main almacena el historial de versiones oficial,(las versiones estables) esta rama se considera que esta lista para entrar a producción .Cuando se lanza un software al publico normalmente se basa en esta rama.
>#### Develop
>Develop se utilizar para probar a integrar funcionalidades nuevas, normalmente no es estable al estar siendo siempre modificada.
>
Entonces a la hora de usarlo, lo primero que debemos hacer es crear la rama `develop`para complementar al `main`, en `develop` guardaremos el historial completo del proyecto mientras que en `main` solo una versión abreviada .
#### Freatures
A su vez cada función nueva creada(**se deben ramificar desde el `develop` a poder ser desde su ultima versión**), debería existir en su propia rama desde la cual enviar al `develop` para que se guarde una copia, estas ramas se llaman `freatures`.
#### Release
Una vez consideremos que `develop` esta listo lo publicaremos en main, esto lo haremos con un `release`(**en esta rama no se puede añadir funciones solo se deberán corregir fallos**).Una vez lista la rama `release` haremos un merge  `main` y `develop` etiquetándolo con el número de la versión.
#### Hotfix
En caso de que la versión del software distribuida(es decir el main) tenga algún fallo se crea una rama Hotfix .**Esta se ramifica desde `main`** y nos permitiría hacer correcciones rápidas del software en producción. Tras ser corregido debería mergearse con la rama `main`y `develop` ,esto debe ir debidamente etiquetado con al versión actualizada
#### Resumidamente

 - Creamos una rama `develop`en base a la `main`.
 - Cuando queramos crear una función se crea en una rama `freature` que posteriormente se mergeara con el `develop`.
 - Cuando queramos mergear `develop` con `main` creamos una rama `release` .
 - Si hay errores en el `main` los solucionaremos en una rama `hotfix` que posteriormente se mergeara.

## Comandos del wrapper de Git-flow

Generalmente se ofrece una serie de comandos simplificados que encapsulan acciones específicas del flujo de trabajo. Ejemplos comunes:

1. Iniciar una nueva característica:
    
    `git feature start <nombre_caracteristica>`
    
2. **Finalizar una característica:**
    
    `git feature finish <nombre_caracteristica>`
    
3. **Iniciar un nuevo lanzamiento**:
`git release start <numero_version>`
4. **Finalizar un lanzamiento:**
    
    `git release finish <numero_version>`
    
5. **Iniciar una nueva corrección de error (hotfix):**
    
    `git hotfix start <nombre_hotfix>`
    
6. **Finalizar una corrección de error (hotfix)**:
`git hotfix finish <nombre_hotfix>`
