# **Instalación de servicios REST/WS Wildfly**

## **Índice**
[Descarga de los ejemplos](#id1)<br>
[Instalación de Servicio Hello-RS](#id2)<br>
[Instalación de Servicio Hello-WS](#id3)

## **Descarga de los ejemplos**<a name = "id1"></a>
Lo primero que haremos será descargarnos los ejemplos de **WildFly Quickstart**.

## **Instalación de Servicio Hello-RS**<a name = "id2"></a>
Una vez descargados los ejemplos ejecutaremos el siguiente comando para complilar el proyecto.

```bash
daw@DLP17-Lubuntu18:~/Desktop/helloworld-ws$ mvn clean install
```

Una vez acabo de compilar, si todo está correcto veremos lo siguiente:

![Compilación correcta](/img/wildfly-s/1.png)

El siguiente paso será desplegar el proyecto, para ello vamos a la sección **Deployments** dentro de WildFly.

En la parte izquierda le daremos al "+" y a **Upload Deployment**.

Lo proximo será seleccionar el **.war**.

![Seleccion del proyecto](/img/wildfly-s/3.png)

En la pestaña siguiente, veremos el nombre que le queremos dar, y si está activado.

![Nombre proyecto](/img/wildfly-s/4.png)

Luego empezará a desplegar el proyecto, si todo ha salido bien, veremos lo siguiente:

![Despliegue correcto](/img/wildfly-s/5.png)

Aquí tenemos la configuración del proyecto.

![Configuración proyecto](/img/wildfly-s/6.png)

Por último visitaremos la página para verificar el correcto funcionamiento de esta.

![Verificación funcionamiento](/img/wildfly-s/7.png)

## **Instalación de Servicio Hello-WS**<a name = "id3"></a>
Como hicimos en el apartado anterior, una vez descargados los ejemplos ejecutaremos el siguiente comando para complilar el proyecto.

```bash
daw@DLP17-Lubuntu18:~/Desktop/helloworld-ws$ mvn clean install
```

Una vez acabo de compilar, si todo está correcto veremos lo siguiente:

![Compilacion correcta](/img/wildfly-s/2.png)

El siguiente paso será desplegar el proyecto, para ello vamos a la sección **Deployments** dentro de WildFly.

En la parte izquierda le daremos al "+" y a **Upload Deployment**.

Lo proximo será seleccionar el **.war**.

![Selecccion proyecto](/img/wildfly-s/8.png)

En la pestaña siguiente, veremos el nombre que le queremos dar, y si está activado.

![Nombre proyecto](/img/wildfly-s/9.png)

Luego empezará a desplegar el proyecto, si todo ha salido bien, veremos lo siguiente:

![Despliegue correcto](/img/wildfly-s/10.png)

Aquí tenemos la configuración del proyecto.

![Configuración proyecto](/img/wildfly-s/11.png)

Por último visitaremos la página para verificar el correcto funcionamiento de esta.

![Verificación funcionamiento](/img/wildfly-s/12.png)
