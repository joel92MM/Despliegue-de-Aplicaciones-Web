<img alt="README-383affa6.png" src="assets/README-383affa6.png" width="" height="" >

<hr/>

# Índice #


## 1. Requisitos básicos ##

## 2. Crear dominio ##

- ### 2.1 Configurar dominio y puertos ###

## 3. Crear subdominio ##

- ### 3.1 Configurar subdominio ###

## 4. Instalar PHP ##

## 5. Instalar MYSQL ##

## 6. Instalar PHPMYADMIN ##
- ### 6.1 Configurar phpmyadmin  ###

<hr/>

**1. Requisitos básicos**

- Disponer de una máquina Ubuntu 20.04
- Internet
- Disponer de un servidor FTP.
- Disponer de Apache instalado

**2. Crear dominio**

<p>En primer lugar crearemos la carpeta con el nombre de dominio, que se encuentra en /var/www/ seguido del nombre de dominio ejemplo **joelmmsystem**, lo hacemos con el siguiente comando</p>

> mkdir -p /var/www/joelmmsystem

<p>Asignaremos los siguientes permisos a la carpeta con el siguiente comando</p>

> chmod -R 755 /var/www/joelmmsystem

<img alt="README-59890652.png" src="assets/README-59890652.png" width="800px"/>

<p>A continuación dentro de la carpeta *joelmmsystem* crearemos la carpeta html que contendrá la pagina principal de nuestro dominio</p>

> mkdir -p /var/www/joelmmsystem/html
> sudo nano /var/www/joelmmsystem/html/index.php

<p>El contenido del index.php será el siguiente: </p>

<img alt="README-4bc6dc9b.png" src="assets/README-4bc6dc9b.png" width="800px"/>

<p>Dentro de la carpeta **html** crearemos la carpeta *errors* que contendrá los archivos para controlar los mensajes de los errores</p>

<img alt="README-135ed77f.png" src="assets/README-135ed77f.png" width="800px"/>

<p>Ahora vamos al archivo de configuración</p>
<p>Localizamos la ruta del archivo sites-available con el siguiente comando</p>

> locate sites-available

<img alt="README-f67bd1d2.png" src="assets/README-f67bd1d2.png" width="800px"/>

<p>Entramos en la ruta </p>

<img alt="README-c20d9257.png" src="assets/README-c20d9257.png" width="" height="">

<br/>
<br/>

- ***2.1 Configurar dominio y puertos***

<p>Crearemos nuestro archvo de configuracion inicial, copiado del original de apache, cuyo nombre sera *joelmmsystem.conf*</p>

<img alt="README-c754c604.png" src="assets/README-c754c604.png" width="800px"/>

<p>Entramos en el archivo de configuracion creado anteriormente con el comando...</p>

> sudo nano joelmmsystem.conf

<p>Configuramos lo siguiente: </p>

> NombreServidor: joelmmsystem
> AliasServidor: www.joelmmsystem.com
> DocumentRoot /var/wwww/joelmmsystem/html

<p>Directorio de la carpetas y permisos</p>

>  <Directory /var/www/joelmmsystem/html> <br/>
        Options Indexes FollowSymLinks<br/>
        AllowOverride None<br/>
        Require all granted<br/>
>    /Directory> <br/>

<p>Archivo de errores</p>

> ErrorDocument 404 /errors/error404.html


<img alt="README-75945b21.png" src="assets/README-75945b21.png" width="800px"/>
<img alt="README-7b21b6b9.png" src="assets/README-7b21b6b9.png" width="800px"/>

<p>Guardamos la configuración CTRL+O Y CTRL+X</p>

<p>Habilitamos la configuracion con el comando </p>

> sudo a2ensite joelmmsystem.conf

<p>Ahora habilitamos el puerto, entramos en la carpeta hosts, con el comando..</p>

>sudo nano /etc/hosts/


<img alt="README-278dfc13.png" src="assets/README-278dfc13.png" width="800px"/>

<p>Reiniciamos nuestro servidor apache con el comando</p>

> sudo systemctl reload apache2.service

<p>Ahora en nuestro navegador ponemos nuestro dominio y se nos mostrara una pagina similar a la siguiente</p>

<img alt="README-0b4125dc.png" src="assets/README-0b4125dc.png" width="800px"/>

<p>Y si introducimos una direccion erronea, se nos mostrara un mensaje de error personalizado</p>

<img alt="README-f806c358.png" src="assets/README-f806c358.png" width="800px"/>

**3. Crear subdominio**

<p></p>
<p></p>
<p></p>
<p></p>
<p></p>
<p></p>
<p></p>
<p></p>
<p></p>
<p></p>

**4. Instalar PHP**

<p></p>
<p></p>
<p></p>
<p></p>
<p></p>
<p></p>
<p></p>
<p></p>
<p></p>
<p></p>

**5. Instalar MYSQL**

<p></p>
<p></p>
<p></p>
<p></p>
<p></p>
<p></p>
<p></p>
<p></p>
<p></p>
<p></p>

**6. Instalar PHPMYADMIN**

<p></p>
<p></p>
<p></p>
<p></p>
<p></p>
<p></p>
<p></p>
<p></p>
<p></p>
<p></p>
