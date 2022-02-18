<img alt="README-e68a36de.png" src="assets/README-e68a36de.png" width="800px"/>

<hr/>

# Índice #

## 1. Creación de dominio principal ##

## 2. Creación de subdominio sftp##

## 3. Creación de subdominio despliegue##

## 4. Verificación de SFTP en cliente subdominio despliegue##

## 5. Creación de subdominio jenkins##

## 6. Creación de pipeline ##



<hr/>

**1. Creación de dominio principal**

Crearemos el fichero de configuración para trabajar con el host virtual, el contenido es el siguiente:

<img alt="README-c73f2137.png" src="assets/README-c73f2137.png" width="800px"/>

<br/>
<br/>

Una vez creado el fichero de configuración crearemos un enlace simbólico desde el archivo de configuración al directorio sites-enabled, con el comando:

> sudo a2ensite nombreFicheroConfiguracion


Comprobamos que no hay errores de sintaxis con el siguiente comando:

> sudo apachectl configtest

Seguidamente crearemos la estructura de directorios en /var/www/


Creamos la carpeta raiz del dominio

<img alt="README-a40321ba.png" src="assets/README-a40321ba.png" width="800px"/>

<br/>
<br/>
Crearemos el contenido de la pagina del dominio principal, index.php el cual sera el siguiente:

<img alt="README-29df1031.png" src="assets/README-29df1031.png" width="800px"/>
<br/>
<br/>

Luego personalizamos el error404 con la siguiente configuración

<img alt="README-b1910dd0.png" src="assets/README-b1910dd0.png" width="800px"/>

A continuación crearemos el nombre de la url que aparecerá en el navegador

<img alt="README-fc6a9197.png" src="assets/README-fc6a9197.png" width="800px"/>

Si introducimos una dirección errónea aparecerá esta imagen

<img alt="README-f5f4b1be.png" src="assets/README-f5f4b1be.png" width="800px"/>

<br/>
<br/>

Si todo ha ido bien reiniciamos el servicio apache2 con el siguiente comando:

> sudo systemctl restart apache2

Visualización del contenido en un navegador web

<img alt="README-df16e136.png" src="assets/README-df16e136.png" width="800px"/>

<br/>
<br/>


**2. Creación de subdominio SFTP**


Crearemos el fichero de configuración para trabajar con el host virtual, el contenido es el siguiente:

<img alt="README-82e5fbdd.png" src="assets/README-82e5fbdd.png" width="800px"/>

Comprobamos que no hay errores de sintaxis con el siguiente comando:

> sudo apachectl configtest

Creamos la carpeta del subdominio

<img alt="README-1e2fc36c.png" src="assets/README-1e2fc36c.png" width="800px"/>

Crearemos el nombre de url del subdominio

<img alt="README-4a00edfb.png" src="assets/README-4a00edfb.png" width="800px"/>

Visualización el correcto funcionamiento del nombre de host en una navegador

<img alt="README-b32dab17.png" src="assets/README-b32dab17.png" width="800px"/>

**3. Creación de subdominio despliegue**

Crearemos el fichero de configuración para trabajar con el host virtual, el contenido es el siguiente:

<img alt="README-1fcf7dfd.png" src="assets/README-1fcf7dfd.png" width="800px"/>

Comprobamos que no hay errores de sintaxis con el siguiente comando:

> sudo apachectl configtest

Creamos la carpeta del subdominio

<img alt="README-083b45f5.png" src="assets/README-083b45f5.png" width="800px"/>

Crearemos el nombre de url del subdominio

<img alt="README-79a22056.png" src="assets/README-79a22056.png" width="800px"/>

Visualización el correcto funcionamiento del nombre de host en una navegador

<img alt="README-a4735f31.png" src="assets/README-a4735f31.png" width="800px"/>

**4. Verificación de SFTP en cliente subdominio despliegue**

Ahora nos crearemos el usuario despliegues con el comandos

> sudo adduser --shell /bin/false nombreUsuario

> contraseña-> 123456789

<img alt="README-9f3f1831.png" src="assets/README-9f3f1831.png" width="800px"/>

Al usuario lo asignamos como propietario de la carpeta despliegue de nuestro dominio con el siguiente comando

> sudo chown usuario:carpeta /var/www/joelmmsystem/nombrecarpeta

<img alt="README-2ec83b1e.png" src="assets/README-2ec83b1e.png" width="800px"/>

Ponemos la carpeta de ese usuario como home con el siguiente comando:

> sudo usermod -d /var/www/joelmmsystem/nombrecarpeta usuarioftp

<img alt="README-3a750adc.png" src="assets/README-3a750adc.png" width="800px"/>

Luego mediante un cliente Filezilla accedemos al servidor wwww.sftp.joelmmsystem.com, el usuario y contraseña que hemos creado de sftp

<img alt="README-52f0b053.png" src="assets/README-52f0b053.png" width="800px"/>

Vemos que se ha establecido conexión

Seguidamente asignaremos los permisos necesarios para ver los archivos subidos

<img alt="README-0904c652.png" src="assets/README-0904c652.png" width="800px"/>

Subimos un archivo de ejemplo, y vemos como se ha subido correctamente

<img alt="README-132d89e5.png" src="assets/README-132d89e5.png" width="800px"/>

El el navegador mediante el subdominio www.despliegue.joelmmsystem.com veremos el archivo index.php

<img alt="README-eff78e22.png" src="assets/README-eff78e22.png" width="800px"/>

**5. Creación de subdominio Jenkins**

Crearemos el fichero de configuración para trabajar con el host virtual, el contenido es el siguiente:


Comprobamos que no hay errores de sintaxis con el siguiente comando:

> sudo apachectl configtest

Crearemos el nombre de url del subdominio
