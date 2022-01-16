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

## 6. Instalación y configuración de PHPMYADMIN ##

## 7. Instalación y configuración de SFTP ##

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

> mkdir -p /var/www/joelmmsystem/html <br/>
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

> NombreServidor: joelmmsystem <br/>
> AliasServidor: www.joelmmsystem.com <br/>
> DocumentRoot /var/wwww/joelmmsystem/html <br/>

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

<p>Creamos una carpeta dentro de joelmmsystem</p>

<img alt="README-3f6cae94.png" src="assets/README-3f6cae94.png" width="800px"/>

<p>Estructura de carpetas de joelmmsystem</p>

<img alt="README-1d34846d.png" src="assets/README-1d34846d.png" width="800px"/>

<p>Posteriormente vamos al archivo de configuración y lo editamos para que acceda a la carpeta </p>

<img alt="README-2be013d6.png" src="assets/README-2be013d6.png" width="800px"/>

<p>Finalmente ya tenemos la carpeta configurada como subdominio</p>

<img alt="README-168b3c21.png" src="assets/README-168b3c21.png" width="800px"/>


**4. Instalar MYSQL**

<p>Antes de instalar mysql, actualizaremos los repositorios de nuestro sistema con el comando..</p>

> sudo apt update && apt upgrade

<p>Ahora procederemos a instalar mysql con el comando..</p>

> sudo apt-get install mysql-server

<img alt="README-75ab7cb3.png" src="assets/README-75ab7cb3.png" width="800px"/>

<p>Presionamos la tecla S y continuamos </p>

<img alt="README-5dafa535.png" src="assets/README-5dafa535.png" width="800px"/>

<p>Tardara unos minutos </p>+

<img alt="README-d12ae188.png" src="assets/README-d12ae188.png" width="800px"/>

<p>Ahora ejecutaremos un script simple de seguridad que nos permite eliminar algunas configuraciones peligrosas y bloquear un poco el acceso a nuestro sistema de BBDD, con el siguiente comando...</p>

> sudo mysql_secure_installation

<img alt="README-affc3fa0.png" src="assets/README-affc3fa0.png" width="800px"/>

<p>A continuación se muestran los pasos a seguir: </p>

<p>Presionamos la tecla n en cada opción..</p>

<img alt="README-333400ae.png" src="assets/README-333400ae.png" width="800px"/>

<p>Introduciremos la nueva contraseña, en nuestro caso sera 123456789</p>

<img alt="README-9722cd87.png" src="assets/README-9722cd87.png" width="800px"/>

<p>Seguimos con la instalación</p>

<img alt="README-0f2b6d8f.png" src="assets/README-0f2b6d8f.png" width="800px"/>
<p></p>
<img alt="README-d51b0605.png" src="assets/README-d51b0605.png" width="800px"/>
<p></p>
<img alt="README-fb89fc00.png" src="assets/README-fb89fc00.png" width="800px"/>
<p></p>
<img alt="README-c821100e.png" src="assets/README-c821100e.png" width="800px"/>

<p>Si hemos realizado los pasos correctamente se nos mostrara un mensaje similar al siguiente</p>

<img alt="README-bdcb40c1.png" src="assets/README-bdcb40c1.png" width="800px"/>


**5. Instalar PHP**

<p>Incluimos algunos paquetes de ayuda, para que el codigo PHP se pueda ejecutar en el servidor Apache y hablar con nuestra base de datos MYSQL, con el siguiente comando..</p>

> sudo apt-get install php libapache2-mod-php php-mysql

<img alt="README-5e2c5f7f.png" src="assets/README-5e2c5f7f.png" width="800px"/>

<p>Buscamos y editamos el archivo dir.conf para ello usamos el siguiente comando...</p>

> locate dir.conf

<img alt="README-614b0a74.png" src="assets/README-614b0a74.png" width="800px"/>

<p>Entramos en la ruta para modificar el archivo, queriendo que apache busque primero archivos .php, se vera de forma similar a la siguiente imagen</p>

<img alt="README-454cbcdc.png" src="assets/README-454cbcdc.png" width="800px"/>
<br/><br/>
<img alt="README-d0a5a105.png" src="assets/README-d0a5a105.png" width="800px"/>

<p>Luego recargamos la configuración de apache con el siguiente comando..</p>

> sudo systemctl reload apache2.service

<p>Comprobamos que se muestra en nuestro navegador</p>

<img alt="README-44737e6c.png" src="assets/README-44737e6c.png" width="800px"/>

**6. Instalación y configuración de PHPMYADMIN**

<p>Nuevamente actualizaremos los repositorios de nuestro sistema con el comando..</p>

> sudo apt-get update

<p>Ahora descargaremos phpmyadmin con el siguiente comando, el cual nos guiara por unos pasos que detallo a continuacion, el comando es..</p>

> sudo apt-get install phpmyadmin php-mbstring

<img alt="README-2e027e3f.png" src="assets/README-2e027e3f.png" width="800px"/>

<p>En la primera pregunta pulsamos la tecla Y, posteriormente se nos mostrara una ventana como la de la imagen</p>

<img alt="README-115d181b.png" src="assets/README-115d181b.png" width="800px"/>

<p>Seleccionamos la primera opcion con la tecla barra espaciadora y seguimos</p>

<img alt="README-115d181b.png" src="assets/README-115d181b.png" width="800px"/>

<p>Se nos preguntara si queremos configurar la base de datos para phpmyadmin pulsamos que si y continuamos</p>

<img alt="README-a9e177b3.png" src="assets/README-a9e177b3.png" width="800px"/>

<p>Ingresamos la nueva contraseña para mysql</p>

<img alt="README-57d38e48.png" src="assets/README-57d38e48.png" width="800px"/>

<p>Confirmamos contraseña anterior</p>

<img alt="README-a056a3f6.png" src="assets/README-a056a3f6.png" width="800px"/>

<p>Ahora habilitamos las extensiones de php con los siguientes comandos..</p>

<img alt="README-4d28915b.png" src="assets/README-4d28915b.png" width="800px"/>
<br/><br/>
<img alt="README-1804f210.png" src="assets/README-1804f210.png" width="800px"/>

<p>Reiniciamos nuestro servidor apache</p>

<p>Iremos a nuestro navegador y entramos en phpmyadmin, ingresamos con usuario root y nuestra contraseña y nos mostrara un mensaje de error como el siguiente</p>

<img alt="README-7cfc29df.png" src="assets/README-7cfc29df.png" width="800px"/>

<p>La solución son los siguientes pasos</p>

<img alt="README-a098d5c2.png" src="assets/README-a098d5c2.png" width="800px"/>
<br/>
<br/>
<img alt="README-99cb7af3.png" src="assets/README-99cb7af3.png" width="800px"/>
<br/>
<br/>
<img alt="README-50478142.png" src="assets/README-50478142.png" width="800px"/>
<br/>
<br/>
<p>Finalmente volveremos a introducir el usuario y contraseña y entraremos en phpmyadmin</p>

<img alt="README-87a44fbe.png" src="assets/README-87a44fbe.png" width="800px"/>


<p>Una vez dentro, procederemos a crear un nuevo usuario, nos vamos a la pestaña cuenta de usuario, bajando nos encontraremos con Agregar cuenta de usuario</p>

<img alt="README-4dc2d8a2.png" src="assets/README-4dc2d8a2.png" width="800px"/>

<p>Agregaremos al nuevo usuario, con su contraseña y los privilegios globales, y pulsamos en continuar..</p>

<img alt="README-d45d462a.png" src="assets/README-d45d462a.png" width="800px"/>
<img alt="README-f9e4c752.png" src="assets/README-f9e4c752.png" width="800px"/>

<p>El resultado es el siguiente</p>

<img alt="README-53ab8df3.png" src="assets/README-53ab8df3.png" width="800px"/>

<p>Como vemos en cuentas de usuario, podemos localizar al usuario nuevo creado</p>

<img alt="README-31384209.png" src="assets/README-31384209.png" width="800px"/>

<p>Ahora probamos a entrar con la nueva cuenta de usuario</p>

<img alt="README-bb7bb9f5.png" src="assets/README-bb7bb9f5.png" width="800px"/>

<p>Vemos el correcto funcionamiento</p>

<img alt="README-dbb5664e.png" src="assets/README-dbb5664e.png" width="800px"/>

**7. Instalación y configuración de SFTP**

<p>Actualizaremos los repositorios de ubuntu</p>

> sudo apt update

<p>Ahora procederemos a instalar SFTP con el comando...</p>

> sudo apt install vsftpd

<img alt="README-451af2af.png" src="assets/README-451af2af.png" width="800px"/>

<p>Nos crearemos un usuario con el comando...</p>

> sudo adduser --shell /bin/false sftp

<img alt="README-83a8a8ab.png" src="assets/README-83a8a8ab.png" width="800px"/>

<p>Intro en todas las opciones, dejando los campos vacíos</p>

<img alt="README-0212daa9.png" src="assets/README-0212daa9.png" width="800px"/>

<p>El usuario creado lo ponemos como propietario de la carpeta sftp de nuestro dominio con el siguiente comando</p>

> sudo chown sftp:sftp /var/www/joelmmsystem/subdomine

<img alt="README-eb8fb667.png" src="assets/README-eb8fb667.png" width="800px"/>

<p>Ponemos la carpeta de ese usuario como home con el siguiente comando </p>

<img alt="README-b6973bcc.png" src="assets/README-b6973bcc.png" width="800px"/>

<p>Buscamos el fichero vsftpd.conf y accedemos al archivo con los comandos....</p>

> locate vsftpd.conf <br/>
> sudo nano .....

<img alt="README-a3d81e4a.png" src="assets/README-a3d81e4a.png" width="800px"/>

<p>Cambiamos la linea *pam_service_name* poniendo como resultado *ftp* como se muestra en la imagen</p>

<img alt="README-2e4d8e3c.png" src="assets/README-2e4d8e3c.png" width="800px"/>

<p>Seleccionamos los permisos para el directorio </p>

<img alt="README-66283f0d.png" src="assets/README-66283f0d.png" width="800px"/>

<p>Nos conectaremos con nuestro localhost, usuario y contraseña</p>

<img alt="README-c293efca.png" src="assets/README-c293efca.png" width="800px"/>

<p>Subiremos un fichero para comprobar la transferencia de archivos </p>
<p>Se ha subido el archivo</p>

<img alt="README-7a1dda54.png" src="assets/README-7a1dda54.png" width="800px"/>

<img alt="README-992eab25.png" src="assets/README-992eab25.png" width="800px"/>

<p>Verificamos en nuestro subdominio que se a subido correctamente</p>

<img alt="README-e72fbd48.png" src="assets/README-e72fbd48.png" width="800px"/>

<hr/>

Enlace github: <a href="https://github.com/joel92MM/Git/tree/main/2ºTrimestre/ConstruccionServicioEmpresa">enlace</a>
