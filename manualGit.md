# Sistema de Control de Versiones

El control de versiones es la práctica de seguir y gestionar los cambios en el código de software. Esto nos hará más fácil ver el seguimiento del trabajo, así como también nos permitirá una manera segura de gestionar nuestro código, es decir, si queremos volver a un punto anterior porque nuestro código se "ha ido de madre", se puede.

También es crucial en entornos de trabajo colaborativos, donde cabe la posibilidad de que varias personas estén haciendo lo mismo, y sobre una teoría se sobrescriba, nos da la opción de elegir con qué versión de las dos queremos quedarnos.

Para evitar esto último, también existe la posibilidad de crear ramas y flujos en el trabajo. Y de una manera diferente, trabajar sobre lo mismo, probarlo lo suficiente, y una vez acabo. Implementarlo al código anterior.

# GIT como la Mejor Alternativa

Ante la amplia variedad de controladores de versiones, Git es el mas usado por practicamente todo el mundo. Un punto importante es que es distribuido y descentralizado, es decir, cada usuario tiene una copia completa de su espacio de trabajo, lo cual facilita el trabajo offline y la colaboración en equipos distribuidos. 

Otro punto importante que sitúa a Git como una buena alternativa es su velocidad y rendimiento, esto se debe a su gran diseño  y a sus potentes algoritmos para operaciones (commit, merge, branch). También algo que caracteriza a Git es su flexibilidad, es decir, la gran capacidad que tiene para adaptarse a diferentes formas de trabajar y fusionar dentro de un grupo de trabajo colaborativo.

Algo que también aporta mucho, es la comunidad activa que tienen y su soporte.

# Funcionamiento externo de GIT

Git se puede utilizar de varias maneras del lado de usuario. 

1. Línea de comandos (CLI).
    
    Git tiene una propia línea de comandos que permite que los usuarios, puedan realizar varias operaciones mediante este método. Algunas de esas operaciones es, crear ramas, realizar commits, fusionar cambios y gestionar conflictos. 
    
2. Interfaz grafica (GUI).
    
    También se integra con interfaces gráficas de usuario que proporiconan una forma visual de interactuar con los repositorios de otra gente. En este modo, tiene unas funcionalidades similares a la liea de comandos, solo que mas fácil e intuitiva. Destacan Github, GitKraken.
    
3. Integración con herramientas de desarrollo. 
    
    También existe la posibilidad de integración de git en los IDEs (Visual Studio, Eclipse), asi como en sistemas de construcción (Maven, Gradle).
    

# Estructura Interna de GIT

La estructura interna de Git se basa en un Modelo de Objetos. Este es fundamental para saber como se almacena la información en un repositorio. 

Los objetos principales son : 

- Blob : representa el contenido de un archivo con un estado especifico.
- Tree (árbol) : representa un directorio y sus contenidos. Contiene referencia a blobs y a otras arboles.
- Commit : representa un punto en el proyecto. Contiene referencia a árboles que representan el estado del proyecto en ese punto en el tiempo, asi como datos sobre el autor del commit, la fecha y el mensaje del commit.
- Tag : es una referencia a un commit específico, utilizado para marcar puntos importantes o saber identificar mejor todos los commits. 
