# **Creación de los Pipeline en distintos Lenguajes**

## **Índice**
[Creación de Pipeline en Java](#id1)<br>
[Creación de Pipeline en Nodejs](#id2)<br>
[Creación de Pipeline en Ruby](#id3)<br>
[Creación de Pipeline en Python](#id4)<br>
[Creación de Pipeline en PHP](#id5)<br>
[Creación de Pipeline en Go](#id6)

## **Creación de Pipeline en Java**<a name = "id1"></a>
En el Panel de Control de Jenkins vamos a **Nueva Tarea**.

![Crear tarea](img/pipeline-jenkins/1.png)

Lo siguiente será **ponerle nombre** y elegir el **tipo**.

![Nombre y tipo](img/pipeline-jenkins/2.png)

Ahora incrustamos el script que quieres que ejecute el pipeline

![Script](img/pipeline-jenkins/3.png)

Ejecutamos el pipeline, nos saldrá el siguiente error:

![Error Docker](img/pipeline-jenkins/4.png)

Para solucionar el error vamos al apartado de **Administrar plugins** de nuestro **Panel de control** y instalamos los siguientes Plugins.

![Instalación Plugins](img/pipeline-jenkins/5.png)

Reiniciamos el servicio de Jenkins al terminar la instalación.

Al volver a ejecutar nos saldrá el siguiente error de permisos.

![Error permisos](img/pipeline-jenkins/7.png)

Para solucionarlo añadiremos el usuario **jenkins** al grupo de **sudoers**.

![Sudoers usuario](img/pipeline-jenkins/8.png)

Volveremos a ejecutar el pipeline, y ahora sí que se ejecutará correctamente.

![Ejecución correcta Java](img/pipeline-jenkins/9.png)

## **Creación de Pipeline en Nodejs**<a name = "id2"></a>
Como en el punto anterior iremos a **Nueva tarea** y le ponemos **nombre** y **tipo**.

![Creación pipeline Node](img/pipeline-jenkins/10.png)

Insertamos el script que ejecutará nuestro pipeline.

![Script](img/pipeline-jenkins/11.png)

Ejecutamos el pipeline y se ejecutará correctamente.

![Ejecución correcta Node](img/pipeline-jenkins/12.png)

## **Creación de Pipeline en Ruby**<a name = "id3"></a>
Como en el punto anterior iremos a **Nueva tarea** y le ponemos **nombre** y **tipo**.

![Creación pipeline Ruby](img/pipeline-jenkins/13.png)

Insertamos el script que ejecutará nuestro pipeline.

![Script](img/pipeline-jenkins/14.png)

Ejecutamos el pipeline y se ejecutará correctamente.

![Ejecución correcta Ruby](img/pipeline-jenkins/15.png)

## **Creación de Pipeline en Python**<a name = "id4"></a>
Como en el punto anterior iremos a **Nueva tarea** y le ponemos **nombre** y **tipo**.

![Creación pipeline Python](img/pipeline-jenkins/16.png)

Insertamos el script que ejecutará nuestro pipeline.

![Script](img/pipeline-jenkins/17.png)

Ejecutamos el pipeline y se ejecutará correctamente.

![Ejecución correcta Python](img/pipeline-jenkins/18.png)

## **Creación de Pipeline en PHP**<a name = "id5"></a>
Como en el punto anterior iremos a **Nueva tarea** y le ponemos **nombre** y **tipo**.

![Creación pipeline PHP](img/pipeline-jenkins/19.png)

Insertamos el script que ejecutará nuestro pipeline.

![Script](img/pipeline-jenkins/20.png)

Ejecutamos el pipeline y se ejecutará correctamente.

![Ejecución correcta PHP](img/pipeline-jenkins/21.png)

## **Creación de Pipeline en Go**<a name = "id6"></a>
Como en el punto anterior iremos a **Nueva tarea** y le ponemos **nombre** y **tipo**.

![Creación pipeline Go](img/pipeline-jenkins/19.png)

Insertamos el script que ejecutará nuestro pipeline.

![Script](img/pipeline-jenkins/20.png)

Ejecutamos el pipeline y se ejecutará correctamente.

![Ejecución correcta Go](img/pipeline-jenkins/21.png)