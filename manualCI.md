 
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
