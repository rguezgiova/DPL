# **Creación de los Pipeline en Php**
    
## **Índice**
[Creación del repositorio y ficheros](#id1)<br>
[Creación del fichero Dockerfile](#id2)<br>
[Creación del fichero Jenkinsfile](#id3)<br>
[Creación del Pipeline](#id4)<br>
[Ejecución del Pipeline](#id5)<br>
[Comprobación](#id6)

## **Creación del repositorio y ficheros**<a name="id1"></a>
Lo primero que haremos será crear un nuevo repositorio en nuestro GitHub llamado **hello-word-php-apache**, dentro de él creamos el directorio **src** con lo siguiente.

![index.php](img/jenkins-php/1.png)

## **Creación del fichero Dockerfile**<a name="id2"></a>
En este paso crearemos el fichero **Dockerfile** con lo siguiente:

![Dockerfile](img/jenkins-php/2.png)

## **Creación del fichero Jenkinsfile**<a name="id3"></a>
Ahora creamos el fichero **Jenkinsfile** con lo siguiente:

![Jenkinsfile](img/jenkins-php/3.png)

## **Creación del Pipeline**<a name="id4"></a>
Lo siguiente que haremos será crear la **Pipeline** para ello vamos al **Panel de control** de Jenkins y creamos una **Nueva tarea**, le ponemos **nombre** y **tipo**.

![Creación Pipeline](img/jenkins-php/4.png)

Seleccionamos la opción de **Git**, pegamos la **URL** de nuestro repositorio, escribimos nuestras credenciales de GitHub, de **Script Path** elegimos **Jenkinsfile** y por último **deseleccionamos** la opción de Checkout.

![Opciones Pipeline](img/jenkins-php/5.png)

## **Ejecución del Pipeline**<a name="id5"></a>
En este paso ejecutaremos nuestro Pipeline creado, si todo ha ido bien debería ejecutarse correctamente.

![Ejecución Pipeline](img/jenkins-php/6.png)

## **Comprobación**<a name="id6"></a>
Por último para comprobar el correcto funcionamiento abrimos un navegador y escribimos en nuestro caso **0.0.0.0:8090** y veremos lo siguiente:

![Comprobación](img/jenkins-php/7.png)
