
<img alt="README-0d42f59c.png" src="assets/README-0d42f59c.png" width="" height="">
<hr/>

# Índice #

## 1. Requisitos básicos ##

## 2. Busquedas de imágenes creadas ##

## 3. Trabajar con la imagen atmoz  ##

## 4. Verificar la imagen ##

*  ### 4.1 Configurar el directorio home en la máquina host ###

## 5. SFTP Multiusuario##


<hr/>

**1. Requisitos básicos**

- Disponer de una máquina Ubuntu 20.04
- Internet

**2. Búsquedas de imágenes creadas**
<p>Podemos consultar las imágenes creadas para la instalación de SFTP, con el comando...</p>

> docker search sftp

![](assets/README-e4379c61.png)

**3. Trabajar con la imagen atmoz**
<p>Para utilizar la imagen desarrollada por <strong>atmoz</strong>, sobre <strong>ftp</strong> realizamos los siguientes pasos </p>

<p>Ejecutamos la imagen, con el comando...</p>

> docker run --name mysftp -p 2294:22 -d atmoz/sftp admin:admin:::upload

![](assets/README-2c7e4cc1.PNG)

<p>donde cada uno de los parámetros representa:</p>

* name, nombre del contenedor mysftp
* admin: admin ::: upload donde foo es el nombre de usuario, pass es la contraseña, upload es el archivo cargado se guardará en el directorio / home / foo / upload en el contenedor. -p 22:22 asigna el puerto 22 del host al puerto 22 del contenedor, de modo que el puerto 22 del host de ubicación se reenviará al puerto 22 del contenedor. -d atmoz / sftp usa la imagen atmoz / sftp en el centro de acoplamiento para crear un contenedor.

**4. Verificar la imagen**

<p>Para verificar la descarga imagen anterior, lanzamos el siguiente comando...</p>

> docker ps | grep sftp

<p>Obtenemos un mensaje similar al siguiente</p>

![](assets/README-5084353f.PNG)

<p>Podemos realizar la prueba de acceso al servidor FTP. Para ello podemos lanzar los siguientes comandos...</p>

> sudo docker ps

![](assets/README-7f298b54.PNG)

<p>Obtenemos informacion detallada del contenedor, con el siguiete comando...</p>

![](assets/README-b7b2344f.PNG)


***4.1 Configurar el directorio home en la maquina host***

<p>Para realizar la configuración del directorio de home de SFTP hemos de ejecutar el siguiente comando:</p>

>   docker run --name mysftp2 -v /host/upload:/home/admin/upload --privileged=true -p 2295:22 -d atmoz/sftp admin:admin:1001

![](assets/README-5a1dc4f9.PNG)

* v / host / upload: / home / admin / upload. Donde el frente de los dos puntos es el directorio del host, la parte posterior se monta en el directorio en el contenedor, si el directorio local / host / uplaod no existe, se creará automáticamente.

* --privileged = true. Debido a las reglas de seguridad de selinux de linux, es necesario agregar privilegios al contenedor.

* --name mysftp2. El nombre también se cambia. Debido a que el nombre no se puede repetir, el puerto también se repite, el contenedor no se iniciará.

## 5. SFTP Multiusuario ##

<p>Ahora configuramos los usuarios para sftp donde...</p>

* Creemos usuarios en el contenedor y asignamos permisos.
* Escribimos archivos de usuario en el host y los montamos en el contenedor.

<p>Utilizaremos el comando..</p>

> docker run --name mysftp3 -v /host/users.conf:/etc/sftp/users.conf:ro -v /home/sftp:/home --privileged=true -p 2296:22 -d atmoz/sftp

![](assets/README-b8a6284f.PNG)

* -v /host/users.conf:/etc/sftp/users.conf:ro mapea el /host/users.conf local al /etc/sftp/users.conf del contenedor, y es de solo lectura en el contenedor.
* -v / home / sftp: / home asigna el directorio local / home / sftp al contenedor / home para almacenar los archivos cargados.

<p>Listamos los contenedores</p>

![](assets/README-e27b05fb.PNG)

<p>Crearemos el archivo /host/users.conf en el directorio local, con el comando..</p>

>   nano /host/users.conf

<p>Introduciendo el siguiente contenido..</p>
<p>
*  xiaoming:123:1001:100<br/>
*  goudan : abc:1002:100<br/>
*  erzhu:xyz:1003:100<br/>
</p>

![](assets/README-c4e70a16.PNG)


![](assets/README-555a55eb.PNG)

<p>Verificamos el funcionamiento a través de un cliente como el filezilla</p>

<img alt="README-f3f800b8.png" src="assets/README-f3f800b8.png" width="800px"/>

<hr/>

Enlace github: <a href="https://github.com/joel92MM/Git/tree/main/2ºTrimestre/Instalacion_Administracion_Servidores_Transferencia_Archivos_Docker">enlace</a>
