 
## Integración continua(CI)
Consiste en automatizar la integración de los cambios de código de varias personas en un proyecto especifico. Permitiendo mergear con el `main` donde se ejecutaran compilaciones y pruebas.
Algo importante es el uso de pruebas automatizadas, los tipos son:
>Son más fáciles y baratas de implementar en el orden en el que aparecen escritas. Siendo así las mas fáciles las unitarias y las de interfaz las mas difíciles.

 - Prueba unitaria: verifican funciones individuales
 - Prueba de integración: verifica el funcionamiento de un conjunto de componentes
 - Prueba de aceptación: sirven para saber si el software cumple los requerimientos del negocio en el que será usado
 - Prueba de interfaz de usuario: comprueba que todo funcione correctamente para el usuario

### USO
Todo esto se ejecutara cada vez que se modifique el `main`,esto lo conseguimos mediante servicios para verificar (existen muchos locales como en la nube).Este lo deberás elegir en función de tu situación y necesidades.
Una vez tengas claro cual vas a necesitar, tienes que instalar el servidor IC independiente. Para esto seguiremos los siguientes pasos:
 - Elegir el servidor que usaremos
 - Preparar el Servidor
 - Instalar el software de IC. Para instalarlo hay varias formas de hacerlo. La principal sería mediante paquetes de instalación específicos para tu sistema operativo. Sin embargo, también existen otras opciones, como en el caso de Jenkins, donde descargaríamos el archivo WAR desde la página oficial de Jenkins y lo ejecutaríamos en un contenedor de servlet compatible.
 - Haríamos la configuración inicial
 - Crearíamos `PIPELINEs`(conjunto automatizado de pasos), crearíamos los que necesitáramos para nuestro proyecto, la forma de definir es personalizada de cada servidor de IC
 - Probar, ajustar y poner en marcha el mantenimiento continuo

### Buenas practicas
 - Al adoptar pruebas automatizadas es recomendable combinarlas con herramientas de cobertura de pruebas para saber que parte del código estas cubriendo con las pruebas. Si bien un porcentaje elevado de cobertura es importante y debemos a aspirar a un alto porcentaje ,es más importante la calidad de estas pruebas
 - Integrar lo antes posible las funciones en el `main`,para así no tenga conflictos si se espera mucho para mergearla
 - Si se rompe el ``main``, la creación de funciones queda en plano secundario el objetivo principal es arreglar el ``main``
 - Asegurarte que todas tus funciones tengan pruebas.

 ## **Herramientas de Integración Continua:**

1. **Jenkins**: es una de las herramientas de integración continua más populares y de código abierto. Permite la automatización de tareas repetitivas relacionadas con el despliegue de software. 
2. **GitLab** CI/CD: GitLab ofrece una solucion integrada. Este permite definir pipelines de manera declarativa en archivos YAML dentro del repositorio, lo que facilita la configuración y mantenimientos. 
3. **Travis CI**: este se integra con GitHub. 

## Runners

Son entornos utilizados para ejecutar tareas de construcción, pruebas y despliegue. Definidas en los pipelines. Estas tareas pueden ejecutar en máquinas físicas o virtuales, incluso en contenedores Docker. El propósito de un runner es ejecutar los scripts definidos en el archivo de configuración.

## Pipelines

Los pipelines son la representación visual de flujos de trabajo automatizados que definen las etapas y acciones que se deben ejecutar. Un pipeline típico puede incluir etapas de construcción, de pruebas unitarias, de pruebas de integración, análisis estático de código y despliegue a entornos de prueba y producción. Cada trabajo puede estar asociado con un runner específico y puede realizar tareas como construir, probar, desplegar y más.

## Stages

También llamadas etapas, son divisiones lógicas dentro de un pipeline que agrupan conjuntos de tareas. Por ejemplo, un pipeline puede tener etapas para construir el código, ejecutar pruebas y desplegar la aplicación. Cada etapa se ejecuta secuencialmente y puede contener una o más tareas.

## Ejemplo de implementación

Primero hay que crear un archivo de configuracion en la ruta .github/workflows. Este archivo sera de extension yml o yaml. En este archivo tiene que estar la configuracion necesaria para la ejecución de CI/CD.

```yaml
name: ci

on:
push:
branches:
- "main"

jobs:
build:
runs-on: ubuntu-latest
steps:
      -
        name: Checkout
        uses: actions/checkout@v4
      -
        name: Login to Docker Hub
        uses: docker/login-action@v3
        with:
          username: ${{ secrets.DOCKERHUB_USERNAME }}
          password: ${{ secrets.DOCKERHUB_TOKEN }}
      -
        name: Set up Docker Buildx
        uses: docker/setup-buildx-action@v3
      -
        name: Build and push
        uses: docker/build-push-action@v5
        with:
          context: .
          file: ./Dockerfile
          push: true
          tags: ${{ secrets.DOCKERHUB_USERNAME }}/clockbox:latest
```

Ahora simplemente ejecuta el workflow. Guarda los  cambios con el commit, y pushea los cambios a la main.
