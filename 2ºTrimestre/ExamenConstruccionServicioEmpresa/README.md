<img alt="README-e68a36de.png" src="assets/README-e68a36de.png" width="800px"/>

<hr/>

# Índice #

## 1. Creación del dominio principal ##

## 2. Creación del subdominio sftp##

## 3. Creación del subdominio despliegue##

## 4. Verificación de SFTP en cliente subdominio despliegue##

## 5. Creación del subdominio jenkins##

## 6. Creación del subdominio phpmyadmin ##

## 7. Creación de pipeline ##



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


<br/>
<br/>

Si todo ha ido bien reiniciamos el servicio apache2 con el siguiente comando:

> sudo systemctl restart apache2

Visualización del contenido en un navegador web

<img alt="README-df16e136.png" src="assets/README-df16e136.png" width="800px"/>



<br/>
<br/>

Si introducimos una dirección errónea aparecerá esta imagen

<img alt="README-f5f4b1be.png" src="assets/README-f5f4b1be.png" width="800px"/>

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

Luego mediante un cliente Filezilla accedemos al servidor www.sftp.joelmmsystem.com, el usuario y contraseña que hemos creado de sftp

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

Redireccionamos la url de jenkins al subdominio que estamos creando, el 301 indica enlace permanente

<img alt="README-02c58d5d.png" src="assets/README-02c58d5d.png" width="800px"/>

Comprobamos que no hay errores de sintaxis con el siguiente comando:

> sudo apachectl configtest

Crearemos el nombre de url del subdominio

<img alt="README-2f8d3ef1.png" src="assets/README-2f8d3ef1.png" width="800px"/>

Visualizamos en el navegador que entramos en jenkins correctamente

<img alt="README-00a34a19.png" src="assets/README-00a34a19.png" width="800px"/>

**6. Creación de subdominio phpmyadmin**

Crearemos el fichero de configuración para trabajar con el host virtual, el contenido es el siguiente:

<img alt="README-f16c8f65.png" src="assets/README-f16c8f65.png" width="800px"/>

Comprobamos que no hay errores de sintaxis con el siguiente comando:

> sudo apachectl configtest

Crearemos el nombre de url del subdominio

<img alt="README-9bf5838f.png" src="assets/README-9bf5838f.png" width="800px"/>

Visualizamos en el navegador que entramos en phpmyadmin correctamente

<img alt="README-68e5c1d6.png" src="assets/README-68e5c1d6.png" width="800px"/>

Nos logeamos con el usuario creado en esta [tarea](https://github.com/joel92MM/Git/tree/main/2%C2%BATrimestre/ConstruccionServicioEmpresa)

<img alt="README-a6b85d2a.png" src="assets/README-a6b85d2a.png" width="800px"/>

Vemos que hemos entrado en phpmyadmin con el usuario

<img alt="README-74d48904.png" src="assets/README-74d48904.png" width="800px"/>

**6. Creación de pipeline**

Entramos en Jenkins mediante el subdominio anteriormente creado

Creamos una tarea pipeline nueva, con el nombre que aparece en la imagen

<img alt="README-377a98ff.png" src="assets/README-377a98ff.png" width="800px"/>

<br/>
<br/>

A continuación nos mostrará la ventana de configuración de la pipeline, iremos a la opción Pipeline y en el script copiamos el contenido de la imagen

<img alt="README-7e3c4887.png" src="assets/README-7e3c4887.png" width="800px"/>

<br/>
<br/>

- El comando de la linea 6 nos permitirá subir el fichero index.php al subdominio sftp.joelmmsystem.com, que se verá en despliegue.joelmmsystem.com

- El comando de la linea 11 nos mostrará la versión instalada en local de MYSQL

- El comando de la linea 12 nos mostrará si la frase que queremos buscar con el comando grep se encuentra en la página solicitada.

- El comando de la linea 13 nos mostrará si la frase que queremos buscar con el comando grep se encuentra en la página solicitada.

- El comando de la linea 14 nos mostrará si la frase que queremos buscar con el comando grep se encuentra en la página solicitada.

Nos muestra la pipeline creada y configurada en el panel de control de Jenkins

<img alt="README-0e5be672.png" src="assets/README-0e5be672.png" width="800px"/>

<br/>
<br/>

Construimos la pipeline

<img alt="README-5d05f5fc.png" src="assets/README-5d05f5fc.png" width="800px"/>

<br/>
<br/>


Nos muestra un error en la salida, vemos el error en los log

<img alt="README-fbc5c9d0.png" src="assets/README-fbc5c9d0.png" width="800px"/>

<br/>
<br/>


Consulto el error, y encuentro el error en está [página](https://stackoverflow.com/questions/12320219/curl-how-to-pass-password-containing-a-percent-sign) al parecer es un error de contraseña, arreglo ese error y vuelvo a construir la Pipeline, y se ha corregido el error, mostrándose correcta

<img alt="README-97f49703.png" src="assets/README-97f49703.png" width="800px"/>

<br/>
<br/>

En el panel de control de jenkins vemos la pipeline que se ha ejecutado sin errores después de varios intentos

<img alt="README-21b6ca9e.png" src="assets/README-21b6ca9e.png" width="800px"/>

<br/>
<br/>

Verificamos en los log que se han ejecutado bien los comandos del script

<img alt="README-dcd06e34.png" src="assets/README-dcd06e34.png" width="800px"/>

<br/>
<br/>

<hr/>

Enlace github: <a href="https://github.com/joel92MM/Git/tree/main/2ºTrimestre/ExamenConstruccionServicioEmpresa">enlace</a>
