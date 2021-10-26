# **Instalación de Nginx en Linux**

## **Índice**
[Instalar Nginx](#id1)<br>
[Aplicar ajustus al Firewall](#id2)<br>
[Comprobar servidor web](#id3)<br>
[Administrar proceso Nginx](#id4)<br>
[Configurar bloques de servidor](#id5)

## **Instalar Nginx**<a name = "id1"></a>
Lo primero que haremos será actualizar los paquetes, haremos lo siguiente:

```bash
daw@DLP17-Lubuntu18:~$ sudo apt update
Obj:1 http://es.archive.ubuntu.com/ubuntu bionic InRelease
Obj:2 http://es.archive.ubuntu.com/ubuntu bionic-updates InRelease             
Obj:3 http://es.archive.ubuntu.com/ubuntu bionic-backports InRelease           
Obj:4 http://security.ubuntu.com/ubuntu bionic-security InRelease              
Obj:6 http://packages.microsoft.com/repos/code stable InRelease                
Obj:5 https://packages.gitlab.com/gitlab/gitlab-ce/ubuntu bionic InRelease     
Leyendo lista de paquetes... Hecho
Creando árbol de dependencias       
Leyendo la información de estado... Hecho
Todos los paquetes están actualizados.
```

Lo siguiente será instalar **Nginx**.

```bash
daw@DLP17-Lubuntu18:~$   sudo apt install nginx
Leyendo lista de paquetes... Hecho
Creando árbol de dependencias       
Leyendo la información de estado... Hecho
El paquete indicado a continuación se instaló de forma automática y ya no es necesario.
  libllvm6.0
Utilice «sudo apt autoremove» para eliminarlo.
Se instalarán los siguientes paquetes adicionales:
  libnginx-mod-http-geoip libnginx-mod-http-image-filter libnginx-mod-http-xslt-filter libnginx-mod-mail
  libnginx-mod-stream nginx-common nginx-core
Paquetes sugeridos:
  fcgiwrap nginx-doc
Se instalarán los siguientes paquetes NUEVOS:
  libnginx-mod-http-geoip libnginx-mod-http-image-filter libnginx-mod-http-xslt-filter libnginx-mod-mail
  libnginx-mod-stream nginx nginx-common nginx-core
0 actualizados, 8 nuevos se instalarán, 0 para eliminar y 0 no actualizados.
Se necesita descargar 597 kB de archivos.
Se utilizarán 2.120 kB de espacio de disco adicional después de esta operación.
¿Desea continuar? [S/n] s
```

## **Aplicar ajustes al Firewall**<a name = "id2"></a>
Ahora configuraremos el **Firewall** para que **Ngnix** tenga acceso, haremos lo siguiente para obtener la lista de las aplicaciones.

```bash
daw@DLP17-Lubuntu18:~$   sudo ufw app list
Aplicaciones disponibles:
  Apache
  Apache Full
  Apache Secure
  CUPS
  Nginx Full
  Nginx HTTP
  Nginx HTTPS
  OpenSSH
```

Ahora habilitaremos el perfil de **Nginx HTTP**.

```bash
daw@DLP17-Lubuntu18:~$   sudo ufw allow 'Nginx HTTP'
Regla añadida
Regla añadida (v6)
```

Verificaremos si se ha habilitado correctamente.

```bash
daw@DLP17-Lubuntu18:~$   sudo ufw status
Estado: activo

Hasta                      Acción      Desde
-----                      ------      -----
Apache                     ALLOW       Anywhere                  
8083/tcp                   ALLOW       Anywhere                  
Nginx HTTP                 ALLOW       Anywhere                  
Apache (v6)                ALLOW       Anywhere (v6)             
8083/tcp (v6)              ALLOW       Anywhere (v6)             
Nginx HTTP (v6)            ALLOW       Anywhere (v6)  
```

## **Comprobar servidor web**<a name = "id3"></a>
Primero verificaremos si el servicio de **Nginx** está activado.

```bash
daw@DLP17-Lubuntu18:~$ systemctl status nginx
● nginx.service - A high performance web server and a reverse proxy server
   Loaded: loaded (/lib/systemd/system/nginx.service; enabled; vendor preset: enabled)
   Active: inactive (dead)
     Docs: man:nginx(8)
```

Ahora cambiaremos el puerto para que pueda iniciar **Ngnix** modificando el fichero **/etc/nginx/sites-enabled/default**.

```bash
listen 8084 default_server;
listen [::]:8084 default_server;
```

Ahora reiniciamos el servicio, y verificaremos el estado, si el paso anterior funcionó correctamente, se iniciará **Nginx**.

```bash
daw@DLP17-Lubuntu18:~$ sudo systemctl status nginx
● nginx.service - A high performance web server and a reverse proxy server
   Loaded: loaded (/lib/systemd/system/nginx.service; enabled; vendor preset: enabled)
   Active: active (running) since Tue 2021-10-26 17:00:06 WEST; 4s ago
     Docs: man:nginx(8)
  Process: 8375 ExecStart=/usr/sbin/nginx -g daemon on; master_process on; (code=exited, status=0/SUCCESS)
  Process: 8374 ExecStartPre=/usr/sbin/nginx -t -q -g daemon on; master_process on; (code=exited, status=0/SUCCESS)
 Main PID: 8376 (nginx)
    Tasks: 5 (limit: 4915)
   CGroup: /system.slice/nginx.service
           ├─8376 nginx: master process /usr/sbin/nginx -g daemon on; master_process on;
           ├─8377 nginx: worker process
           ├─8378 nginx: worker process
           ├─8379 nginx: worker process
           └─8380 nginx: worker process

oct 26 17:00:06 DLP17-Lubuntu18 systemd[1]: Starting A high performance web server and a reverse proxy server...
oct 26 17:00:06 DLP17-Lubuntu18 systemd[1]: Started A high performance web server and a reverse proxy server.
```

## **Administrar proceso de Nginx**<a name = "id4"></a>
Ahora vamos a detener nuestro servidor.

```bash
daw@DLP17-Lubuntu18:~$ sudo systemctl stop nginx
```

Lo volveremos a arrancar.

```bash
daw@DLP17-Lubuntu18:~$ sudo systemctl start nginx
```

Lo reiniciaremos.

```bash
daw@DLP17-Lubuntu18:~$ sudo systemctl restart nginx
```

Lo recargamos.

```bash
daw@DLP17-Lubuntu18:~$  sudo systemctl reload nginx
```

Desabilitaremos el inicio automático.

```bash
daw@DLP17-Lubuntu18:~$ sudo systemctl disable nginx
Synchronizing state of nginx.service with SysV service script with /lib/systemd/systemd-sysv-install.
Executing: /lib/systemd/systemd-sysv-install disable nginx
```

Y por último habilitaremos el inicio automático.

```bash
daw@DLP17-Lubuntu18:~$ sudo systemctl enable nginx
Synchronizing state of nginx.service with SysV service script with /lib/systemd/systemd-sysv-install.
Executing: /lib/systemd/systemd-sysv-install enable nginx
```

## **Configurar bloques de servidor**<a name = "id5"></a>
Vamos a crear un directorio en la ruta **/var/www** con nuestro nombre.

```bash
daw@DLP17-Lubuntu18:~$ sudo mkdir -p /var/www/giovanni/html
```

Lo siguiente será darle la propiedad del directorio a la variable de entorno **$USER**.

```bash
daw@DLP17-Lubuntu18:~$ sudo chown -R $USER:$USER /var/www/giovanni/html/
```

Ahora asignaremos los permisos del directorio en **755*, esto hará que el propietario tenga todos los permisos, pero su grupo y el resto de usuarios solo lectura.

```bash
daw@DLP17-Lubuntu18:~$ sudo chmod -R 755 /var/www/giovanni/
```

Ahora crearemos una página **index.html**.

```bash
daw@DLP17-Lubuntu18:~$ sudo nano /var/www/giovanni/html/index.html
```

Con el siguiente contenido:

```bash
<html>
    <head>
        <title>Welcome to giovanni!</title>
    </head>
        <body>
           <h1>Success!  The giovanni server block is working!</h1>
        </body>
</html>
```

Ahora crearemos un archivo de configuración nuevo para nuestro bloque en la ruta **/etc/nginx/sites-available/giovanni** con el siguiente contenido.

```bash
server {
    listen 8084;
    listen [::]:8084;

    root /var/www/giovanni/html
    index index.html index.htm index.nginx-debian.html;

    server_name giovanni www.giovanni;

    location / {
        try_files $uri $uri/ =404;
    }
}
```

Ahora de ese mismo fichero de configuración le realizaremos un enlace simbólico a la ruta **/etc/nginx/sites-enabled**.

```bash
daw@DLP17-Lubuntu18:~$ sudo ln -s /etc/nginx/sites-available/giovanni /etc/nginx/sites-enabled/
```

Ahora para evitar un problema de memoria habilitaremos la directiva **server_names_hash_bucket_size** en el siguiente fichero.

```bash
daw@DLP17-Lubuntu18:~$ sudo nano /etc/nginx/nginx.conf
```

Ahora comprobaremos si todo lo anterior está sin errores de sintaxis.

```bash
daw@DLP17-Lubuntu18:~$ sudo nginx -t
nginx: the configuration file /etc/nginx/nginx.conf syntax is ok
nginx: configuration file /etc/nginx/nginx.conf test is successful
```

Ahora reiniciaremos el servicio.

```bash
daw@DLP17-Lubuntu18:~$ sudo systemctl restart nginx.service
```