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

# Comandos principales (de alto nivel)

### git-add[1]

Agrega el contenido de ficheros al índice.
>Ejemplo: git-add archivo_modificado.txt

### git-am[1]

Aplicar una serie de parches desde una carpeta de correo electrónico.
>Ejemplo: `git-am < patches_email.txt` aplica los parches que tenemos en el archivo

### git-archive[1]

Crear un archivo de ficheros desde un árbol con nombre.
>Ejemplo: `git-archive --format=zip --output=archivo.zip master` para crear un archivo ZIP en un árbol que esta en una rama master.

### git-bisect[1]

Busca mediante binario la confirmación que metió un bug. Esta tiene muchas opciones 
>Ejemplo de funcionamiento: 
>`git-bisect start` inicia el proceso de búsqueda
>`git-bisect good <commit-id>`  marca si una confirmación es buena o no de manera manual
>`git-bisect bad HEAD` si la sesión actual tuviera un error la marcaríamos como mala

### git-branch[1]

Sirve para listar, crear, o borrar ramas.
>Ejemplo: `git-branch nueva_rama` crea una rama

### git-bundle[1]

Mover objetos y referencias por archivo.
>Ejemplo: `git bundle create mi_repositorio.bundle master`` crea un archivo bundle en master con el cual podremos clonar después

### git-checkout[1]

Cambia de ramas o restaura los ficheros del árbol de trabajo.
>Ejemplo: ``git checkout feature/nueva-funcionalidad`` cambiaria a la rama 'feature/nueva-funcionalidad'.

### git-cherry-pick[1]

Aplica los cambios introducidos por algunas confirmaciones existentes.
>Ejemplo: `git cherry-pick <tu-hash>` dentro de una rama especifica haces el commit del hash.

### git-citool[1]

Alternativa gráfica a git-commit(raramente usado).
>Ejemplo: `git citool` abre el interfaz

### git-clean[1]

Elimina ficheros no rastreados del árbol de trabajo.
>Ejemplos: 
>`git clean -f` para eliminar todos los archivos no rastreados de forma forzada. 
>`git clean -n`haria una simulación de los archivos que borrarías

### git-clone[1]

Clona un repositorio en un directorio nuevo.
>Ejemplo: `git clone https://github.com/user/repo.git` 

### git-commit[1]

Hace un commit.
>Ejemplo: `git commit -m "Mensaje del commit"` 

### git-describe[1]

Le da un nombre a un objeto que todos podamos entender
>Ejemplo: `git describe --tags` me mostraría `<tag>-<num-commits>-g<hash>`

### git-diff[1]

Se utiliza para ver las diferencias entre distintas versiones.
>Ejemplo: `git diff` nos enseñaría la diferencia entre la área de preparación y la área de trabajo

### git-fetch[1]

Descarga objetos y referencias desde otro repositorio.
>Ejemplo: `git fetch origin` para descargar los cambios del repositorio desde 'origin'.

### git-format-patch[1]

Genera archivos de parches a partir de los commits de git
>Ejemplo: `git format-patch origin/master` para generar archivos de parches para todos los commits que están en la rama 'master' del repositorio remoto 'origin'.

### git-gc[1]

Limpia ficheros innecesarios y optimiza el repositorio local.
>Ejemplo: `git gc` tiene varias opciones como --auto o --agresive que sirven para recolectar basura de forma auto o recolectar basura de forma agresiva

### git-grep[1]

Sirve para buscar patrones
>Ejemplo: `git grep "buscar_texto"`busca patrones

### git-gui[1]

Una interfaz gráfica portable para Git.
>Ejemplo: `git gui` para abrir la interfaz gráfica de Git.

### git-init[1]

Crea un repositorio de Git vacío o reinicializa uno ya existente.
>Ejemplo: `git init nuevo_proyecto` inicia un nuevo repositorio

### git-log[1]

Muestra los registros de las commits.
>Ejemplo: `git log --oneline` para mostrar el historial de commits en una sola línea. 

### git-maintenance[1]

Ejecuta tareas para optimizar los datos de un repositorio Git.
>Ejemplo: `git maintenance start` inicia las tareas de mantenimiento

### git-merge[1]

Fusiona ramas de git
>Ejemplo: `git merge otra_rama` fusiona la rama actual con la "otra_rama"

### git-mv[1]

Mueve o cambia el nombre a un fichero, un directorio o un enlace simbólico.
>Ejemplo: `git mv archivo.txt nuevo_nombre.txt` para cambiar el nombre de un archivo.

### git-notes[1]

Agregar, ver, editar o eliminar notas de objetos.
>Ejemplo: `git notes add -m "Nota sobre esta confirmación"` para agregar una nota a una confirmación.

### git-pull[1]

Obtiene y fusiona los datos de un repositorio remoto.
>Ejemplo: `git pull origin master` 

### git-push[1]

Envía los cambios locales de un repositorio.
>Ejemplo: `git push origin master` 

### git-range-diff[1]

Compara dos rangos de commits en un repositorio.
>Ejemplo: `git range-diff <rango1>..<rango2>` compara dos rangos de commits

### git-rebase[1]

Vuelve a aplicar confirmaciones en otra rama.

### git-reset[1]

Restablece el estado de git a un estado en especifico
>Ejemplo: 
>`
>git reset --hard <hash_de_la_confirmación>
>`

### git-restore[1]

Restaura ficheros del árbol de trabajo.
>Ejemplo: Para restaurar un archivo específico a su estado en el último commit:
>`
>git restore archivo.txt
>`

### git-revert[1]

Revierte algunas confirmaciones existentes.
>Ejemplo:
>`
>git revert HEAD
>`

### git-rm[1]

Elimina ficheros del árbol de trabajo y del índice.
>Ejemplo: 
>`
>git rm archivo.txt
>`

### git-shortlog[1]

Resume el resultado de git log.
>Ejemplo: 
>`
>git shortlog
>`

### git-show[1]

Muestra información de varios tipos de objetos.
>Ejemplo: mostrará los detalles de la etiqueta hash
>`
>git show <hash>
>`

### git-sparse-checkout[1]

Reducir el árbol de trabajo a un subconjunto de ficheros rastreados en mi repositorio para descargar y mantener solo ciertas partes de tu proyecto si fuera necesario.
>Ejemplo: Para configurar un sparse checkout para incluir solo ciertos directorios:
>`
>git sparse-checkout init --cone
>git sparse-checkout set directorio1/ directorio2/
>`

### git-stash[1]

Permite poner en una reserva los cambios de un directorio de trabajo con cambios. Es para cuando necesitas realizar una operación que necesita un directorio de trabajo limpio, pero aún no estás listo para confirmar tus cambios.
>Ejemplo: Para guardar los cambios en stash:
>`
>git stash push
>`

### git-status[1]

Muestra el estado del árbol de trabajo.
>Ejemplo: Para ver el estado del repositorio:
>`
>git status
>`

### git-submodule[1]

Inicializa, actualiza o inspecciona submódulos.
>Ejemplo: Para inicializar un submodulo:
>`
>git submodule add <URL_del_submódulo> <directorio_destino>
>`

### git-switch[1]

Cambiar de rama.
>Ejemplo: 
>`
>git switch rama_a_cambiar
>`

### git-tag[1]

Crea, lista, elimina o verifica un objeto de etiqueta firmado con GPG.
>Ejemplo: Para crear una etiqueta firmada con GPG:
>`
>git tag -s v1.0 -m "Versión 1.0"
>`

### git-worktree[1]

Gestiona múltiples árboles de trabajo.
>Ejemplo:Crear un arbol de trabajo
>`
>git worktree add <ruta_nueva_rama> <nombre_de_la_rama>
>`

### gitk[1]

El navegador de repositorio Git(con interfaz grafica).

### scalar[1]

Una herramienta para administrar repositorios Git grandes.
>Ejemplo: Para ejecutar una operación scalar:
>Tienes muchas opciones para completar el comando
>`
>scalar <comando>
>`

# Comandos Auxiliares
Podemos subdividir estos en:
## Para Manipular
### git-config[1]

Obtener o establecer opciones de repositorio o globales.
>Ejemplo: Para establecer el nombre de usuario :
>`
>git config user.name "Tu Nombre"
>`

### git-fast-export[1]

Exportador de datos de Git.
>Ejemplo: exportar el historial de commits:
>`
>git fast-export --all > exportacion.git
>`

### git-fast-import[1]

Una herramienta para importadores de datos de Git.
>Ejemplo: Importar archivos de datos_importados.git:
>`
>git fast-import < datos_importados.git
>`

### git-filter-branch[1]

Sirve para reescribir ramas ya creadas
>Ejemplo: Eliminar un archivo de seguimiento del historial:
>`
>git filter-branch --tree-filter 'rm -f archivo.txt' HEAD
>`

### git-mergetool[1]

Sirve para ayudar a resolver conflictos de mergo utilizando herramientas de resolución.
>Ejemplo: Resolver conflictos de fusión usando meld:
>`
>git mergetool -t meld
>`

### git-pack-refs[1]

Empaqueta heads y etiquetas para un acceso eficiente al repositorio.
>Ejemplo: Empaquetar todas las referencias:
>`
>git pack-refs --all
>`

### git-prune[1]

Limpia todos los objetos no alcanzables de la base de datos de objetos.
>Ejemplo:
>`
>git prune
>`

### git-reflog[1]

Muestra el registro de referencia de Git
>Ejemplo: Ver el registro de referencia de HEAD:
>`
>git reflog HEAD
>`

### git-remote[1]

Gestiona un conjunto de repositorios con seguimiento.
>Ejemplo: Agregar un nuevo repositorio remoto:
>`
>git remote add origin <url_del_repositorio>
>`

### git-repack[1]

Empaquetar objetos no empaquetados en un repositorio.
>Ejemplo: Empaqueta objetos sueltos y los guarda en archivos pack
>`
>git repack -d
>`

### git-replace[1]

Crear, listar, eliminar referencias para reemplazar objetos.
>Ejemplo:
>`
>git replace <hash_de_la_confirmación>
>`

## Interrogadores

### git-annotate[1]

Anotar líneas de fichero con información de commits.
>Ejemplo:
>`
>git annotate archivo.txt
>`

### git-blame[1]

Muestra qué revisión y autor modificaron por última vez cada línea de un fichero.
>Ejemplo: Ver quién modificó cada línea de un archivo::
>`
>git blame archivo.txt
>`

### git-bugreport[1]

Recolectar información para el usuario para generar un reporte de bug.
>Ejemplo: Creaun informe de bug :
>`
>git bugreport
>`

### git-count-objects[1]

Contar el número de objetos no empaquetados y su consumo de espacio en disco.
>Ejemplo: Contar los objetos no empaquetados en el repositorio:
>`
>git count-objects -v
>`

### git-diagnose[1]

Genera un archivo zip de información de diagnóstico.
>Ejemplo: 
>`
>git diagnose
>`

### git-difftool[1]

Mostrar diferencias entre los cambios realizados en un archivo o entre dos commits utilizando una herramienta externa
>Ejemplo: Mostrar diferencias usando kdiff3:
>`
>git difftool -t kdiff3
>`

### git-fsck[1]

Verifica la conectividad y validez de los objetos en la base de datos.
>Ejemplo: 
>`
>git fsck
>`

### git-help[1]

Mostrar información de ayuda sobre Git.
>Ejemplo: Mostrar la ayuda para commit:
>`
>git help commit
>`

### git-instaweb[1]

Navegar instantáneamente a tu repositorio de trabajo en gitweb.

### git-merge-tree[1]

Realiza merge sin tocar el índice o el árbol de trabajo.
>Ejemplo: Hacer merge de dos arboles
>`
>git merge-tree <base> <rama1> <rama2>
>`

### git-rerere[1]

Reutilizar la resolución guardada de fusiones con conflictos(De ahi lo de re re re).

### git-show-branch[1]

Mostrar ramas y sus confirmaciones.
>Ejemplo:
>`
>git show-branch
>`

### git-verify-commit[1]

Verificar la firma GPG de los commits.
>Ejemplo: 
>`
>git verify-commit <hash_de_la_confirmación>
>`

### git-verify-tag[1]

Verificar la firma GPG de etiquetas.
>Ejemplo: 
>`
>git verify-tag <nombre_de_la_etiqueta>
>`

### git-version[1]

Mostrar información de la versión de Git.


### git-whatchanged[1]

Mostrar logs con lo que ha cambiado por cada commit hecho

### gitweb[1]

Interfaz web de Git (interfaz web para repositorios Git).

