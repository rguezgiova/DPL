# ** Instalación de Docker en Linux**

## **Índice**
[Instalar Docker](#id1)
[Trabajar con imágenes de Docker](#id2)
[Administrar contenedores de Docker](#id3)

## **Instalar Docker**<a name = "id1"></a>
Lo primero que haremos será actualizar la lista de paquetes.

```bash
daw@DLP17-Lubuntu18:~$ sudo apt update
Obj:1 http://es.archive.ubuntu.com/ubuntu bionic InRelease
Obj:2 http://security.ubuntu.com/ubuntu bionic-security InRelease              
Obj:4 http://es.archive.ubuntu.com/ubuntu bionic-updates InRelease             
Obj:5 http://es.archive.ubuntu.com/ubuntu bionic-backports InRelease           
Obj:6 http://packages.microsoft.com/repos/code stable InRelease                
Obj:3 https://packages.gitlab.com/gitlab/gitlab-ce/ubuntu bionic InRelease     
Leyendo lista de paquetes... Hecho
Creando árbol de dependencias       
Leyendo la información de estado... Hecho
Se pueden actualizar 13 paquetes. Ejecute «apt list --upgradable» para verlos.
```

Ahora instalaremos algunos paquetes de requisitos previos para usar apt a través de HTTPS.

```bash
daw@DLP17-Lubuntu18:~$ sudo apt install apt-transport-https ca-certificates curl software-properties-common
Leyendo lista de paquetes... Hecho
Creando árbol de dependencias       
Leyendo la información de estado... Hecho
ca-certificates ya está en su versión más reciente (20210119~18.04.2).
curl ya está en su versión más reciente (7.58.0-2ubuntu3.16).
software-properties-common ya está en su versión más reciente (0.96.24.32.14).
apt-transport-https ya está en su versión más reciente (1.6.14).
El paquete indicado a continuación se instaló de forma automática y ya no es necesario.
  libllvm6.0
Utilice «sudo apt autoremove» para eliminarlo.
0 actualizados, 0 nuevos se instalarán, 0 para eliminar y 13 no actualizados.
```

Añadiremos la clave GPG para el repositorio de Docker.

```bash
daw@DLP17-Lubuntu18:~$ curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo apt-key add -
OK
```

Ahora agregamos el repositorio de Docker a nuestras fuentes de APT.

```bash
daw@DLP17-Lubuntu18:~$ sudo add-apt-repository "deb [arch=amd64] https://download.docker.com/linux/ubuntu focal stable"
Obj:1 http://es.archive.ubuntu.com/ubuntu bionic InRelease
Des:2 https://download.docker.com/linux/ubuntu focal InRelease [57,7 kB]                                            
Obj:3 http://security.ubuntu.com/ubuntu bionic-security InRelease                                                   
Obj:4 http://es.archive.ubuntu.com/ubuntu bionic-updates InRelease                                        
Des:6 https://download.docker.com/linux/ubuntu focal/stable amd64 Packages [12,3 kB]                                
Obj:7 http://es.archive.ubuntu.com/ubuntu bionic-backports InRelease                                                
Obj:5 https://packages.gitlab.com/gitlab/gitlab-ce/ubuntu bionic InRelease                                      
Obj:8 http://packages.microsoft.com/repos/code stable InRelease                                    
Descargados 70,0 kB en 2s (42,8 kB/s)   
Leyendo lista de paquetes... Hecho
```

Actualizaremos los paquetes con los paquetes de Docker.

```bash
daw@DLP17-Lubuntu18:~$ sudo apt update
Obj:1 http://es.archive.ubuntu.com/ubuntu bionic InRelease
Obj:2 http://es.archive.ubuntu.com/ubuntu bionic-updates InRelease                                                  
Obj:3 http://es.archive.ubuntu.com/ubuntu bionic-backports InRelease                                                
Obj:4 https://download.docker.com/linux/ubuntu focal InRelease                                                      
Obj:5 http://security.ubuntu.com/ubuntu bionic-security InRelease                                                   
Obj:6 https://packages.gitlab.com/gitlab/gitlab-ce/ubuntu bionic InRelease                                          
Obj:7 http://packages.microsoft.com/repos/code stable InRelease                                     
Leyendo lista de paquetes... Hecho
Creando árbol de dependencias       
Leyendo la información de estado... Hecho
Se pueden actualizar 13 paquetes. Ejecute «apt list --upgradable» para verlos.
```

Nos aseguramos que la instalación será desde el repositorio de Docker.

```bash
daw@DLP17-Lubuntu18:~$ apt-cache policy docker-ce
docker-ce:
  Instalados: (ninguno)
  Candidato:  5:20.10.10~3-0~ubuntu-focal
  Tabla de versión:
     5:20.10.10~3-0~ubuntu-focal 500
        500 https://download.docker.com/linux/ubuntu focal/stable amd64 Packages
     5:20.10.9~3-0~ubuntu-focal 500
        500 https://download.docker.com/linux/ubuntu focal/stable amd64 Packages
     5:20.10.8~3-0~ubuntu-focal 500
        500 https://download.docker.com/linux/ubuntu focal/stable amd64 Packages
     5:20.10.7~3-0~ubuntu-focal 500
        500 https://download.docker.com/linux/ubuntu focal/stable amd64 Packages
     5:20.10.6~3-0~ubuntu-focal 500
        500 https://download.docker.com/linux/ubuntu focal/stable amd64 Packages
     5:20.10.5~3-0~ubuntu-focal 500
        500 https://download.docker.com/linux/ubuntu focal/stable amd64 Packages
     5:20.10.4~3-0~ubuntu-focal 500
        500 https://download.docker.com/linux/ubuntu focal/stable amd64 Packages
     5:20.10.3~3-0~ubuntu-focal 500
        500 https://download.docker.com/linux/ubuntu focal/stable amd64 Packages
     5:20.10.2~3-0~ubuntu-focal 500
        500 https://download.docker.com/linux/ubuntu focal/stable amd64 Packages
     5:20.10.1~3-0~ubuntu-focal 500
        500 https://download.docker.com/linux/ubuntu focal/stable amd64 Packages
     5:20.10.0~3-0~ubuntu-focal 500
        500 https://download.docker.com/linux/ubuntu focal/stable amd64 Packages
     5:19.03.15~3-0~ubuntu-focal 500
        500 https://download.docker.com/linux/ubuntu focal/stable amd64 Packages
     5:19.03.14~3-0~ubuntu-focal 500
        500 https://download.docker.com/linux/ubuntu focal/stable amd64 Packages
     5:19.03.13~3-0~ubuntu-focal 500
        500 https://download.docker.com/linux/ubuntu focal/stable amd64 Packages
     5:19.03.12~3-0~ubuntu-focal 500
        500 https://download.docker.com/linux/ubuntu focal/stable amd64 Packages
     5:19.03.11~3-0~ubuntu-focal 500
        500 https://download.docker.com/linux/ubuntu focal/stable amd64 Packages
     5:19.03.10~3-0~ubuntu-focal 500
        500 https://download.docker.com/linux/ubuntu focal/stable amd64 Packages
     5:19.03.9~3-0~ubuntu-focal 500
        500 https://download.docker.com/linux/ubuntu focal/stable amd64 Packages
```

Por último instalaremos Docker.

```bash
daw@DLP17-Lubuntu18:~$ sudo apt install docker-ce
Leyendo lista de paquetes... Hecho
Creando árbol de dependencias       
Leyendo la información de estado... Hecho
El paquete indicado a continuación se instaló de forma automática y ya no es necesario.
  libllvm6.0
Utilice «sudo apt autoremove» para eliminarlo.
Se instalarán los siguientes paquetes adicionales:
  containerd.io docker-ce-cli docker-ce-rootless-extras docker-scan-plugin pigz
Paquetes sugeridos:
  aufs-tools cgroupfs-mount | cgroup-lite
Paquetes recomendados:
  slirp4netns
Se instalarán los siguientes paquetes NUEVOS:
  containerd.io docker-ce docker-ce-cli docker-ce-rootless-extras docker-scan-plugin pigz
0 actualizados, 6 nuevos se instalarán, 0 para eliminar y 13 no actualizados.
Se necesita descargar 95,2 MB de archivos.
Se utilizarán 402 MB de espacio de disco adicional después de esta operación.
¿Desea continuar? [S/n] s
```

Verificaremos si el servicio está activo.

```bash
daw@DLP17-Lubuntu18:~$ sudo systemctl status docker
● docker.service - Docker Application Container Engine
   Loaded: loaded (/lib/systemd/system/docker.service; enabled; vendor preset: enabled)
   Active: active (running) since Tue 2021-11-02 16:45:22 WET; 9s ago
     Docs: https://docs.docker.com
 Main PID: 3961 (dockerd)
    Tasks: 10
   CGroup: /system.slice/docker.service
           └─3961 /usr/bin/dockerd -H fd:// --containerd=/run/containerd/containerd.sock
```

## **Trabajar con imágenes de Docker**<a name = "id2"></a>
Ahora verificaremos si podemos acceder y descargar las imágenes de Docker Hub.

```bash
daw@DLP17-Lubuntu18:~$ docker run hello-world
docker: Got permission denied while trying to connect to the Docker daemon socket at unix:///var/run/docker.sock: Post "http://%2Fvar%2Frun%2Fdocker.sock/v1.24/containers/create": dial unix /var/run/docker.sock: connect: permission denied.
```

Para arreglar este error de permisos, haremos lo siguiente:

```bash
daw@DLP17-Lubuntu18:~$ sudo chmod 666 /var/run/docker.sock
```

Volvemos a probar.

```bash
daw@DLP17-Lubuntu18:~$ docker run hello-world
Unable to find image 'hello-world:latest' locally
latest: Pulling from library/hello-world
2db29710123e: Pull complete 
Digest: sha256:37a0b92b08d4919615c3ee023f7ddb068d12b8387475d64c622ac30f45c29c51
Status: Downloaded newer image for hello-world:latest

Hello from Docker!
This message shows that your installation appears to be working correctly.

To generate this message, Docker took the following steps:
 1. The Docker client contacted the Docker daemon.
 2. The Docker daemon pulled the "hello-world" image from the Docker Hub.
    (amd64)
 3. The Docker daemon created a new container from that image which runs the
    executable that produces the output you are currently reading.
 4. The Docker daemon streamed that output to the Docker client, which sent it
    to your terminal.
```

## **Administrar contenedores de Docker**<a name = "id3"></a>
Para ver todos los contenedores activos haremos lo siguiente:

```bash
daw@DLP17-Lubuntu18:~$ sudo docker ps
CONTAINER ID   IMAGE     COMMAND   CREATED   STATUS    PORTS     NAMES
```

Para ver todos los contenedores, activos o inactivos, usaremos lo siguiente:

```bash
daw@DLP17-Lubuntu18:~$ sudo docker ps -a
CONTAINER ID   IMAGE         COMMAND    CREATED         STATUS                     PORTS     NAMES
f45405fa4e1d   hello-world   "/hello"   3 minutes ago   Exited (0) 3 minutes ago             sad_albattani
```

Para ver el último contenedor creado.

```bash
daw@DLP17-Lubuntu18:~$ sudo docker ps -l
CONTAINER ID   IMAGE         COMMAND    CREATED         STATUS                     PORTS     NAMES
f45405fa4e1d   hello-world   "/hello"   4 minutes ago   Exited (0) 4 minutes ago             sad_albattani
```

Para listar las imágenes de Docker.

```bash
daw@DLP17-Lubuntu18:~$ sudo docker images
REPOSITORY    TAG       IMAGE ID       CREATED       SIZE
hello-world   latest    feb5d9fea6a5   5 weeks ago   13.3kB
```