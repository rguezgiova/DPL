# **Instalación y Adminsitración de Servidores de Transferencia de archivos**

## **Índice**
[Trabajar con la imagen](#id1)<br>
[Verificar la imagen](#id2)

## **Trabajar con la imagen**<a name = "id1"></a>
Lo primero que haremos será buscar la imagen que vamos a usar.

```bash
daw@budgie21:~/docker$ docker search sftp
NAME                      DESCRIPTION                                     STARS     OFFICIAL   AUTOMATED
atmoz/sftp                Easy to use SFTP server                         405                  [OK]
```

Ahora descargaremos la imagen.

```bash
daw@budgie21:~/docker$ docker run --name ftp -p 2294:22 -d atmoz/sftp admin:admin:::upload
Unable to find image 'atmoz/sftp:latest' locally
latest: Pulling from atmoz/sftp
c4cc477c22ba: Pull complete 
b6fadfc81766: Pull complete 
713959244109: Pull complete 
27c7410c332e: Pull complete 
d0c9cf2389e0: Pull complete 
Digest: sha256:15989f8af35125619eea94bac65ab8fdb4fcda6f53f2f22104bffb037ca601c5
Status: Downloaded newer image for atmoz/sftp:latest
df284f26ce38e750ac1a09118ae2820e6fa5585768cbb4e5cea56ff63f049fdd
```

Configuraremos el directorio **home** de **SFTP**.

```bash
daw@budgie21:~/docker$ docker run --name ftp2 -v /host/upload:/home/admin/upload --privileged=true -p 2295:22 -d atmoz/sftp admin:admin:1001
0a150624261cea9357958dbc97b7571bdc9bee7c43e48181fc6705b00f55d1fb
```

Por último configuraremos el servidor FTP para el uso de múltiples usuarios.

```bash
daw@budgie21:~/docker$ docker run --name ftp3 -v /host/users.conf:/etc/sftp/users.conf:ro -v /home/sftp:/home --privileged=true -p 2296:22 -d atmoz/sftp
6f21d4745269dbcc1a7ede16bef6fc0d466b3cc06b1e86f6397f4a42b5de0b99
```

Tendremos que crear el fichero **/host/users.conf** para el uso de este.

```bash
  usuario1:123:1001:100
  usuario2:abc:1002:100
  usuario3:xyz:1003:100
```

## **Verificar la imagen**<a name = "id2"></a>
Ahora verificaremos la imagen, para ello, usaremos el siguiente comando:

```bash
daw@budgie21:~/docker$ docker ps | grep ftp
df284f26ce38   atmoz/sftp   "/entrypoint admin:a…"   2 minutes ago   Up 2 minutes   0.0.0.0:2294->22/tcp, :::2294->22/tcp   ftp
```

Verificaremos la IP de nuestro servidor FTP.

```bash
daw@budgie21:~/docker$ docker inspect df284f26ce38 | grep "IPAddress"
            "SecondaryIPAddresses": null,
            "IPAddress": "172.17.0.2",
                    "IPAddress": "172.17.0.2",
```

