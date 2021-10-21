# **Instalación de WildFly en Linux**

## **Índice**
[Actualización de repositorios](#id1)<br>
[Instalación de WildFly](#id2)<br>
[Configuración de WildFly](#id3)<br>
[Acceso a WildFly](#id4)<br>
[Añadir usuarios a WildFly](#id5)

## **Actualización de repositorios**<a name = "id1"></a>
Antes de comenzar con la instalación actualizaremos los repositorios.

```bash
daw@DLP17-Lubuntu18:~$   sudo apt update && sudo apt upgrade
Obj:1 http://es.archive.ubuntu.com/ubuntu bionic InRelease
Des:2 http://security.ubuntu.com/ubuntu bionic-security InRelease [88,7 kB]                                         
Des:4 http://es.archive.ubuntu.com/ubuntu bionic-updates InRelease [88,7 kB]                                        
Des:5 http://es.archive.ubuntu.com/ubuntu bionic-backports InRelease [74,6 kB]                                      
Obj:6 http://packages.microsoft.com/repos/code stable InRelease                                                     
Des:7 http://security.ubuntu.com/ubuntu bionic-security/main amd64 DEP-11 Metadata [50,3 kB]                       
Obj:3 https://packages.gitlab.com/gitlab/gitlab-ce/ubuntu bionic InRelease                                      
Des:8 http://security.ubuntu.com/ubuntu bionic-security/universe amd64 DEP-11 Metadata [59,0 kB]           
Des:9 http://es.archive.ubuntu.com/ubuntu bionic-updates/main i386 Packages [1.370 kB]         
Des:10 http://security.ubuntu.com/ubuntu bionic-security/multiverse amd64 DEP-11 Metadata [2.464 B]    
Des:11 http://es.archive.ubuntu.com/ubuntu bionic-updates/main amd64 Packages [2.277 kB]                            
Des:12 http://es.archive.ubuntu.com/ubuntu bionic-updates/main amd64 DEP-11 Metadata [292 kB]
Des:13 http://es.archive.ubuntu.com/ubuntu bionic-updates/restricted amd64 Packages [513 kB]
Des:14 http://es.archive.ubuntu.com/ubuntu bionic-updates/restricted i386 Packages [28,8 kB]
Des:15 http://es.archive.ubuntu.com/ubuntu bionic-updates/universe amd64 Packages [1.759 kB]
Des:16 http://es.archive.ubuntu.com/ubuntu bionic-updates/universe i386 Packages [1.582 kB]
Des:17 http://es.archive.ubuntu.com/ubuntu bionic-updates/universe amd64 DEP-11 Metadata [300 kB]
Des:18 http://es.archive.ubuntu.com/ubuntu bionic-updates/multiverse amd64 DEP-11 Metadata [2.464 B]
Des:19 http://es.archive.ubuntu.com/ubuntu bionic-backports/universe amd64 DEP-11 Metadata [9.268 B]
Descargados 8.497 kB en 3s (2.682 kB/s)                               
Leyendo lista de paquetes... Hecho
Creando árbol de dependencias       
Leyendo la información de estado... Hecho
Todos los paquetes están actualizados.
Leyendo lista de paquetes... Hecho
Creando árbol de dependencias       
Leyendo la información de estado... Hecho
Calculando la actualización... Hecho
Los paquetes indicados a continuación se instalaron de forma automática y ya no son necesarios.
  libllvm6.0 linux-headers-4.15.0-20 linux-headers-4.15.0-20-generic linux-image-4.15.0-20-generic
  linux-modules-4.15.0-20-generic linux-modules-extra-4.15.0-20-generic
Utilice «sudo apt autoremove» para eliminarlos.
0 actualizados, 0 nuevos se instalarán, 0 para eliminar y 0 no actualizados.
```

## **Instalación de WildFly**<a name = "id2"></a>
Ahora realizaremos la instalación de **WildFly**, para ello la descargaremos de su página web.

```bash
daw@DLP17-Lubuntu18:~/Descargas$   wget https://github.com/wildfly/wildfly/releases/download/25.0.0.Final/wildfly-25.0.0.Final.tar.gz
--2021-10-21 14:50:06--  https://github.com/wildfly/wildfly/releases/download/25.0.0.Final/wildfly-25.0.0.Final.tar.gz
Resolviendo github.com (github.com)... 140.82.121.4
Conectando con github.com (github.com)[140.82.121.4]:443... conectado.
Petición HTTP enviada, esperando respuesta... 302 Found
Ubicación: https://github-releases.githubusercontent.com/764708/ef6a6350-a4cc-4a89-a20b-cc175681c590?X-Amz-Algorithm=AWS4-HMAC-SHA256&X-Amz-Credential=AKIAIWNJYAX4CSVEH53A%2F20211021%2Fus-east-1%2Fs3%2Faws4_request&X-Amz-Date=20211021T135009Z&X-Amz-Expires=300&X-Amz-Signature=39a9b95865bb2f1a64ea4fb27b89b693e8ba769ff5b8be10e5020c8e323aa621&X-Amz-SignedHeaders=host&actor_id=0&key_id=0&repo_id=764708&response-content-disposition=attachment%3B%20filename%3Dwildfly-25.0.0.Final.tar.gz&response-content-type=application%2Foctet-stream [siguiente]
--2021-10-21 14:50:07--  https://github-releases.githubusercontent.com/764708/ef6a6350-a4cc-4a89-a20b-cc175681c590?X-Amz-Algorithm=AWS4-HMAC-SHA256&X-Amz-Credential=AKIAIWNJYAX4CSVEH53A%2F20211021%2Fus-east-1%2Fs3%2Faws4_request&X-Amz-Date=20211021T135009Z&X-Amz-Expires=300&X-Amz-Signature=39a9b95865bb2f1a64ea4fb27b89b693e8ba769ff5b8be10e5020c8e323aa621&X-Amz-SignedHeaders=host&actor_id=0&key_id=0&repo_id=764708&response-content-disposition=attachment%3B%20filename%3Dwildfly-25.0.0.Final.tar.gz&response-content-type=application%2Foctet-stream
Resolviendo github-releases.githubusercontent.com (github-releases.githubusercontent.com)... 185.199.108.154, 185.199.109.154, 185.199.110.154, ...
Conectando con github-releases.githubusercontent.com (github-releases.githubusercontent.com)[185.199.108.154]:443... conectado.
Petición HTTP enviada, esperando respuesta... 200 OK
Longitud: 220044335 (210M) [application/octet-stream]
Guardando como: “wildfly-25.0.0.Final.tar.gz”

wildfly-25.0.0.Final.tar.gz   100%[==============================================>] 209,85M  32,9MB/s    en 6,4s    

2021-10-21 14:50:13 (32,8 MB/s) - “wildfly-25.0.0.Final.tar.gz” guardado [220044335/220044335]
```

El siguiente paso será crear un nuevo grupo para **WildFly**.

```bash
daw@DLP17-Lubuntu18:~/Descargas$ sudo groupadd -r wildfly
```

Y un nuevo usuario.

```bash
daw@DLP17-Lubuntu18:~/Descargas$ sudo useradd -r -g wildfly -d /opt/wildfly -s /sbin/nologin wildfly
```

Luego **descomprimiremos** el paquete.

```bash
daw@DLP17-Lubuntu18:~/Descargas$ tar -xvzf wildfly-25.0.0.Final.tar.gz 
wildfly-25.0.0.Final/domain/configuration/application-roles.properties
wildfly-25.0.0.Final/domain/configuration/domain.xml
wildfly-25.0.0.Final/domain/configuration/logging.properties
wildfly-25.0.0.Final/domain/configuration/host.xml
wildfly-25.0.0.Final/domain/configuration/mgmt-groups.properties
wildfly-25.0.0.Final/domain/configuration/default-server-logging.properties
wildfly-25.0.0.Final/domain/configuration/host-slave.xml
wildfly-25.0.0.Final/domain/configuration/host-master.xml
wildfly-25.0.0.Final/domain/configuration/application-users.properties
wildfly-25.0.0.Final/domain/configuration/mgmt-users.properties
```

Y lo moveremos a la ubicación que va a ocupar, en este caso **/opt/wildfly**.

```bash
daw@DLP17-Lubuntu18:~/Descargas$ sudo mv wildfly-25.0.0.Final /opt/wildfly
```

Creamos un enlace simbólico al directorio.

```bash

```

Ahora le daremos permisos al usuario y grupo **wildfly**.

```bash
daw@DLP17-Lubuntu18:~$ sudo chown -R wildfly:wildfly /opt/wildfly
```

Lo siguiente será configurar e iniciar el servicio.

```bash
daw@DLP17-Lubuntu18:~$ sudo mkdir -p /etc/wildfly

daw@DLP17-Lubuntu18:~$ sudo cp /opt/wildfly/docs/contrib/scripts/systemd/wildfly.conf /etc/wildfly/
```

Continuaremos configurando el arranque, para ello tendremos que lanzar los siguientes comandos:

```bash
daw@DLP17-Lubuntu18:~$ sudo cp /opt/wildfly/docs/contrib/scripts/systemd/launch.sh /opt/wildfly/bin/

daw@DLP17-Lubuntu18:~$ sudo sh -c 'chmod +x /opt/wildfly/bin/*.sh'

daw@DLP17-Lubuntu18:~$ sudo cp /opt/wildfly/docs/contrib/scripts/systemd/wildfly.service /etc/systemd/system/

daw@DLP17-Lubuntu18:~$ sudo systemctl daemon-reload
```

Ya podremos iniciar el servicio.

```bash
daw@DLP17-Lubuntu18:~$ sudo systemctl start wildfly
```

Verfificaremos el estado del servicio.

```bash
daw@DLP17-Lubuntu18:~$ sudo systemctl status wildfly
● wildfly.service - The WildFly Application Server
   Loaded: loaded (/etc/systemd/system/wildfly.service; disabled; vendor preset: enabled)
   Active: active (running) since Thu 2021-10-21 15:12:50 WEST; 34s ago
 Main PID: 20812 (launch.sh)
    Tasks: 63 (limit: 4915)
   CGroup: /system.slice/wildfly.service
           ├─20812 /bin/bash /opt/wildfly/bin/launch.sh standalone standalone.xml 0.0.0.0
           ├─20813 /bin/sh /opt/wildfly/bin/standalone.sh -c standalone.xml -b 0.0.0.0
           └─20906 java -D[Standalone] -server -Xms64m -Xmx512m -XX:MetaspaceSize=96M -XX:MaxMetaspaceSize=256m -Djav

oct 21 15:12:50 DLP17-Lubuntu18 systemd[1]: Started The WildFly Application Server.
```

Y también configuraremos el inicio automático del servicio.

```bash
daw@DLP17-Lubuntu18:~$ sudo systemctl enable wildfly
Created symlink /etc/systemd/system/multi-user.target.wants/wildfly.service → /etc/systemd/system/wildfly.service.
```

## **Configuración de WildFly**<a name = "id3"></a>
En este apartado configuraremos **WildFly** para permitir el tráfico por un puerto específico, para ello, modificaremos el siguiente fichero.

```bash
daw@DLP17-Lubuntu18:~$ sudo nano /opt/wildfly/standalone/configuration/standalone.xml
```

Modificando la siguiente línea:

```bash
<socket-binding name="http" port="${jboss.http.port:8083}"/>
```

Por último permitiremos el tráfico por el puerto.

```bash
daw@DLP17-Lubuntu18:~$ sudo ufw allow 8083/tcp
Regla añadida
Regla añadida (v6)
```

## **Acceso a WildFly**<a name = "id4"></a>
Para acceder a **WildFly** usaremos la IP: **http://localhost:8083/**.

![Visualización de la pag principal de WildFly](/img/wildfly/15.png)

## **Añadir usuarios a WildFly**<a name = "id5"></a>
Primero añadiremos el usuario administrador.

```bash
daw@DLP17-Lubuntu18:~$ sudo /opt/wildfly/bin/add-user.sh

What type of user do you wish to add? 
 a) Management User (mgmt-users.properties) 
 b) Application User (application-users.properties)
(a): a

Enter the details of the new user to add.
Using realm 'ManagementRealm' as discovered from the existing property files.
Username : daw
Password recommendations are listed below. To modify these restrictions edit the add-user.properties configuration file.
 - The password should be different from the username
 - The password should not be one of the following restricted values {root, admin, administrator}
 - The password should contain at least 8 characters, 1 alphabetic character(s), 1 digit(s), 1 non-alphanumeric symbol(s)
Password : 
WFLYDM0097: Password should not be equal to 'admin', this value is restricted.
Are you sure you want to use the password entered yes/no? yes
Re-enter Password : 
What groups do you want this user to belong to? (Please enter a comma separated list, or leave blank for none)[  ]: 
About to add user 'daw' for realm 'ManagementRealm'
Is this correct yes/no? yes
Added user 'daw' to file '/opt/wildfly/standalone/configuration/mgmt-users.properties'
Added user 'daw' to file '/opt/wildfly/domain/configuration/mgmt-users.properties'
Added user 'daw' with groups  to file '/opt/wildfly/standalone/configuration/mgmt-groups.properties'
Added user 'daw' with groups  to file '/opt/wildfly/domain/configuration/mgmt-groups.properties'
Is this new user going to be used for one AS process to connect to another AS process? 
e.g. for a slave host controller connecting to the master or for a Remoting connection for server to server Jakarta Enterprise Beans calls.
yes/no? yes
To represent the user add the following to the server-identities definition <secret value="YWRtaW4=" />
```
