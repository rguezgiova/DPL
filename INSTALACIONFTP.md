# **Instalación y Adminsitración de Transferencia de archivos**

## **Ínice**
[Instalación de FTP](#id1)<br>
[Instalación de FileZilla](#id2)<br>
[Configuración de FTP](#id3)

## **Instalación de FTP**<a name = "id1"></a>
Lo primero que haremos será actualizar los repositorios.

```bash
daw@budgie21:~$ sudo apt update
Obj:1 https://download.docker.com/linux/ubuntu focal InRelease
Obj:2 http://es.archive.ubuntu.com/ubuntu impish InRelease                                              
Obj:3 http://security.ubuntu.com/ubuntu impish-security InRelease                                       
Obj:4 http://es.archive.ubuntu.com/ubuntu impish-updates InRelease
Obj:5 http://es.archive.ubuntu.com/ubuntu impish-backports InRelease
Obj:6 https://deb.nodesource.com/node_16.x impish InRelease
Leyendo lista de paquetes... Hecho
Creando árbol de dependencias... Hecho
Leyendo la información de estado... Hecho
```

Lo siguiente será instalar **FTP**.

```bash
daw@budgie21:~$ sudo apt install vsftpd
Leyendo lista de paquetes... Hecho
Creando árbol de dependencias... Hecho
Leyendo la información de estado... Hecho
Se instalarán los siguientes paquetes NUEVOS:
  vsftpd
0 actualizados, 1 nuevos se instalarán, 0 para eliminar y 0 no actualizados.
```

En el siguiente paso permitiremos el acceso a los puertos.

```bash
daw@budgie21:~$ sudo ufw allow ftp
Reglas actualizadas
Reglas actualizadas (v6)
```

También permitiremos el puerto de datos.

```bash
daw@budgie21:~$ sudo ufw allow ftp-data
Reglas actualizadas
Reglas actualizadas (v6)
```

## **Instalación de FileZilla**<a name = "id2"></a>
Ahora instalaremos el cliente **FileZilla**.

```bash
daw@budgie21:~$ sudo apt install filezilla
Leyendo lista de paquetes... Hecho
Creando árbol de dependencias... Hecho
Leyendo la información de estado... Hecho
Se instalarán los siguientes paquetes adicionales:
  filezilla-common libfilezilla11 libpugixml1v5 libwxbase3.0-0v5 libwxgtk3.0-gtk3-0v5
Se instalarán los siguientes paquetes NUEVOS:
  filezilla filezilla-common libfilezilla11 libpugixml1v5 libwxbase3.0-0v5 libwxgtk3.0-gtk3-0v5
0 actualizados, 6 nuevos se instalarán, 0 para eliminar y 0 no actualizados.
Se necesita descargar 9.942 kB de archivos.
Se utilizarán 40,9 MB de espacio de disco adicional después de esta operación.
```

Verificamos que nos podemos conectar al servidor.

![Test conexion](img/ftp-insalacion/6.png)

## **Configuración de FTP**<a name = "id3"></a>
Ahora configuraremos el modo pasivo, para ello, editaremos el fichero **vsftpd.conf** y añadiremos lo siguiente:

```bash
pasv_enable=YES
pasv_min_port=30000
pasv_max_port=30050
```

Reiniciaremos el servicio.

```bash
daw@budgie21:~$ sudo systemctl restart vsftpd
```

Permitiremos al Firewall el acceso con los puertos seleccionados.

```bash
daw@budgie21:~$ sudo ufw allow 30000:30050/tcp
Reglas actualizadas
Reglas actualizadas (v6)
```

Verificamos que estamos en modo pasivo.

```bash
ftp> passive
Passive mode on.
```

Ahora dejaremos que los usuarios del sistema se puedan conectar, para ello descomentaremos lo siguiente dentro del fichero de configuración:

```bash
local_enable=YES
```

Lo siguiente será dejar que los usuarios puedan crear o eliminar ficheros y directorios, descomentaremos lo siguiente:

```bash
write_enable=YES
```

También enjaularemos a los usuarios para que solo puedan añadir o eliminar en su propia carpeta personal, para ello haremos lo siguiente:

```bash
chroot_local_user=YES
```

Y para evitar que eliminen ficheros esenciales para el sistema, descomentaremos lo siguiente:

```bash
allow_writeable_chroot=YES
```