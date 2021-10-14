# **Despliegue de War en Apache-Tomcat**

## **Índice**
[Requisitos previos](#id1)<br>
[Construcción del proyecto](#id2)

## **Requisitos previos**<a name = "id1"></a>
Ya que tenemos ya instalado **Java**, ahora instalaremos **Maven**.

```bash
daw@DLP17-Lubuntu18:~$  sudo apt install maven
Leyendo lista de paquetes... Hecho
Creando árbol de dependencias       
Leyendo la información de estado... Hecho
El paquete indicado a continuación se instaló de forma automática y ya no es necesario.
  libllvm6.0
Utilice «sudo apt autoremove» para eliminarlo.
Se instalarán los siguientes paquetes adicionales:
  libaopalliance-java libapache-pom-java libatinject-jsr330-api-java libcdi-api-java libcommons-cli-java
  libcommons-io-java libcommons-lang3-java libcommons-parent-java libgeronimo-annotation-1.3-spec-java
  libgeronimo-interceptor-3.0-spec-java libguava-java libguice-java libhawtjni-runtime-java libjansi-java
  libjansi-native-java libjsr305-java libmaven-parent-java libmaven-resolver-java libmaven-shared-utils-java
  libmaven3-core-java libplexus-cipher-java libplexus-classworlds-java libplexus-component-annotations-java
  libplexus-interpolation-java libplexus-sec-dispatcher-java libplexus-utils2-java libsisu-inject-java
  libsisu-plexus-java libslf4j-java libwagon-file-java libwagon-http-shaded-java libwagon-provider-api-java
Paquetes sugeridos:
  libaopalliance-java-doc libatinject-jsr330-api-java-doc libservlet3.1-java libcommons-io-java-doc
  libcommons-lang3-java-doc libasm-java libcglib-java libjsr305-java-doc libmaven-shared-utils-java-doc
  liblogback-java libplexus-cipher-java-doc libplexus-classworlds-java-doc libplexus-interpolation-java-doc
  libplexus-sec-dispatcher-java-doc libplexus-utils2-java-doc junit4 testng libcommons-logging-java
  liblog4j1.2-java
Se instalarán los siguientes paquetes NUEVOS:
  libaopalliance-java libapache-pom-java libatinject-jsr330-api-java libcdi-api-java libcommons-cli-java
  libcommons-io-java libcommons-lang3-java libcommons-parent-java libgeronimo-annotation-1.3-spec-java
  libgeronimo-interceptor-3.0-spec-java libguava-java libguice-java libhawtjni-runtime-java libjansi-java
  libjansi-native-java libjsr305-java libmaven-parent-java libmaven-resolver-java libmaven-shared-utils-java
  libmaven3-core-java libplexus-cipher-java libplexus-classworlds-java libplexus-component-annotations-java
  libplexus-interpolation-java libplexus-sec-dispatcher-java libplexus-utils2-java libsisu-inject-java
  libsisu-plexus-java libslf4j-java libwagon-file-java libwagon-http-shaded-java libwagon-provider-api-java
  maven
0 actualizados, 33 nuevos se instalarán, 0 para eliminar y 1 no actualizados.
Se necesita descargar 8.915 kB de archivos.
Se utilizarán 11,8 MB de espacio de disco adicional después de esta operación.
¿Desea continuar? [S/n] s
```

Ahora verificaremos la instalación haciendo lo siguiente:

```bash
daw@DLP17-Lubuntu18:~$ mvn --version
Apache Maven 3.6.0
Maven home: /usr/share/maven
Java version: 11.0.11, vendor: Ubuntu, runtime: /usr/lib/jvm/java-11-openjdk-amd64
Default locale: es_ES, platform encoding: UTF-8
OS name: "linux", version: "4.15.0-159-generic", arch: "amd64", family: "unix"
```

## **Construcción del proyecto**<a name = "id2"></a>
Ahora iremos al proyecto y realizaremos los siguientes cambios en el fichero **web.xml**:

```bash
<display-name>app-web-giovanni</display-name>
```

Haremos lo mismo en **index.jsp**.

```bash
<p>Yo soy Giovanni</p>
```

Luego de esto lanzaremos el comando **mvn clean install**.

```bash
[INFO] ------------------------------------------------------------------------
[INFO] BUILD SUCCESS
[INFO] ------------------------------------------------------------------------
[INFO] Total time:  19.776 s
[INFO] Finished at: 2021-10-13T16:15:17+01:00
[INFO] ------------------------------------------------------------------------
```

Ahora movemos el fichero **.war** a la carpeta **webapps** de **Tomcat**.

```bash
daw@DLP17-Lubuntu18:~/Desktop/proyecto$ sudo mv target/app-web-giovanni.war /opt/tomcat/apache-tomcat/webapps/
```
