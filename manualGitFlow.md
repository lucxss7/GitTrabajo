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
