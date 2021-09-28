## **Manipulación de repositorios de Git**

## **Índice** 
1. [Configuración](#id1)
2. [Creación de un repositorio](#id2)
3. [Comprobar el estado del repositorio](#id3)
4. [Realizando Commit´s](#id4)
5. [Modificación de ficheros](#id5)
6. [Historial](#id6)

### **Configuración**<a name = "id1"></a>
Lo primero que haremos será la configuración de Git definiendo nuestro nombre de usuario y correo electrónico.

![Configuración de usuario y correo electrónico](img/manipulacion/1.png)

También activaremos el color de la salida de los comandos, mostraremos la configuración final luego de todo.

![Configuración del color de salida](img/manipulacion/2.png)

### **Creación de un repositorio**<a name = "id2"></a>
Ahora crearemos el directorio **DPL**, nos moveremos a él e iniciaremos git, lanzamos el comando **ls -la** al final para ver que se han creado las dependencias de Git dentro.

![Creación del directorio DPL, iniciación de Git en él y comprobación de las dependencias de Git](img/manipulacion/3.png)

### **Comprobar el estado del repositorio**<a name = "id3"></a>
Ahora comprobaremos el estado del repositorio.

![Comprobación del estado del directorio](img/manipulacion/4.png)

Crearemos el fichero **indice.txt**, y en él añadimos lo siguiente:

![Creación del fichero indice.txt con datos introducidos](img/manipulacion/5.png)

Guardaremos el contenido el fichero y volveremos a ver el estado del repositorio, veremos que se ha añadido a la lista de “Archivos sin seguimiento” el fichero que hemos creado.

![Comprobación del estado dle repositorio](img/manipulacion/6.png)

Ahora añadiremos el fichero a la zona de intercambio.

![Añadido el fichero a la zona de intercambio local](img/manipulacion/7.png)

Y volveremos a comprobar el estado del repositorio, ahora como vemos, ya el cambio está esperando a ser confirmado.

![Comprobación del directorio](img/manipulacion/8.png)

### **Realizando Commit´s**<a name = "id4"></a>
En este paso lo primero que haremos será realizar un commit de los cambios realizados anteriormente con el mensaje “Añadido índice de la asignatura DPL.”.

![Realización del primer commit](img/manipulacion/9.png)

Luego de esto, veremos el estado del repositorio.

![Comprobar estado del repositorio](img/manipulacion/10.png)

### **Modificación de ficheros**<a name = "id5"></a>
Modificaremos el fichero creado anteriormente y le añadiremos lo siguiente:

![Modificación del fichero añadiendo información adicional](img/manipulacion/11.png)

Ahora mostraremos los cambios en comparación a la última versión que existe en el repositorio, veremos los dos capítulos añadidos.

![Comprobación de los cambios realizados](img/manipulacion/12.png)

Por último añadiremos un nuevo commit con el mensaje “Añadido los capítulos 3  y 4”.

![Realización de un commit nuevo](img/manipulacion/13.png)

### **Historial**<a name = "id6"></a>
En este paso mostraremos los cambios de la última versión subida al repositorio con respecto de la anterior.

![Comprobación de cambios respecto al directorio](img/manipulacion/14.png)

Lo próximo que haremos será cambiar el mensaje del último commit a “Añadido el capitulo sobre gestión de ramas al índice.”.

![Actualización del mensaje de commit](img/manipulacion/15.png)

Por último volveremos a mostrar los cambios al repositorio.

![Comprobación de los cambios en el repositorio](img/manipulacion/16.png)
