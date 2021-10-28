

<img src="assets/prueba-050196f8.png" alt="portada" width="800px"/>

<br/>
<hr/>

# Índice #

## 1. Requisitos previos para la instalación ##


## 2. Pasos para instalar y configurar Ngnix ##

*  ## 2.1 Instalar Nginx ##

*  ## 2.2 Aplicar ajustes al firewall ##

*  ## 2.3 Comprobar su servidor web ##

*  ## 2.4 Administrar el proceso de Nginx ##

*  ## 2.5 Configurar bloques de servidor ##

<hr/>

**1. Requisitos  previos a la instalación**

<p>Tener un S.O. Ubuntu 20.04 con un cuenta de superusuario no root. </p>


**2. Pasos para instalar y configurar Nginx**

***2.1 Instalar Nginx***

<p>Primeramente antes de instalar nginx, actualizaremos nuestro indice local de repositorios de paquetes, teniendo acceso a los listados de paquetes más recientes, con el siguiente comando...</p>

> sudo apt update

<p>Una vez finalizada, la actualización de paquetes , instalaremos nginx, nos instalara cualquier dependencia necesaria en su servidor, ejecutando el siguiente comando</p>

> sudo apt install Nginx

***2.2 Aplicar ajustes al firewall***

<p>Mostraremos un listado de los perfiles de la aplicación, con el siguiente comando..</p>

> sudo ufw app list

<p>Se mostrará un listado como el siguiente</p>

***2.3 Comprobar su servidor web***

<p>Ahora verificamos que el servicio esté en ejecución, con el siguiente comando..</p>

> systemctl status Nginx

<p>Nos mostrará los siguiente</p>

***2.4 Administrar el proceso de Nginx***

<p>Ahora vamos a revisar algunos comandos básicos para comprobar que todo esta bien</p>

<p>Detenemos el servidor web, escribiendo</p>

> sudo systemctl stop nginx

<p>Iniciamos el servidor web</p>

> sudo systemctl start nginx


***2.5 Configurar bloques de servidor***
