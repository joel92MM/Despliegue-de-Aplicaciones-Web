<img alt="README-e68a36de.png" src="assets/README-e68a36de.png" width="" height="" >

<hr/>

# Índice #


## 1. Creación de dominio principal ##

## 2. Creación de subdominio sftp##

## 3. Creación de subdominio despliegue##

## 4. Creación de subdominio jenkins##



**1. Creación de dominio principal**

Crearemos el fichero de configuración para trabajar con el host virtual, el contenido es el siguiente:

Una vez creado el fichero de configuración crearemos un enlace simbólico desde el archivo de configuración al directorio sites-enabled, con el comando:

> sudo a2ensite nombreFicheroConfiguracion


Comprobamos que no hay errores de sintaxis con el siguiente comando:

> sudo apachectl configtest

Seguidamente crearemos la estructura de directorios en /var/www/

Luego crearemos el fichero index.php con el contenido siguiente:

A continuación crearemos el nombre de la url que aparecerá en el navegador

Si todo ha ido bien reiniciamos el servicio apache2 con el siguiente comando:

> sudo systemctl restart apache2

Visualización del contenido en un navegador web


**1. Creación de subdominio SFTP**
