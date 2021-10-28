

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

<img alt="Prueba-92bd8ffa.png" src="assets/Prueba-92bd8ffa.png" width="800PX">

<p>Una vez finalizada, la actualización de paquetes , instalaremos nginx, nos instalara cualquier dependencia necesaria en su servidor, ejecutando el siguiente comando</p>

> sudo apt install Nginx

<img alt="Prueba-94b8baad.png" src="assets/Prueba-94b8baad.png" width="800px">

***2.2 Aplicar ajustes al firewall***

<p>Mostraremos un listado de los perfiles de la aplicación, con el siguiente comando..</p>

> sudo ufw app list

<p>Se mostrará un listado como el siguiente</p>

<img alt="Prueba-8fc51085.png" src="assets/Prueba-8fc51085.png" width="800px">


***2.3 Comprobar su servidor web***

<p>Ahora verificamos que el servicio esté en ejecución, con el siguiente comando..</p>

> systemctl status Nginx

<p>Nos mostrará los siguiente</p>

<img alt="Prueba-0ec587ab.png" src="assets/Prueba-0ec587ab.png" width="800px">

***2.4 Administrar el proceso de Nginx***

<p>Ahora vamos a revisar algunos comandos básicos para comprobar que todo esta bien</p>

<p>Detenemos el servidor web, escribiendo</p>

> sudo systemctl stop nginx

<img alt="Prueba-e1640ac7.png" src="assets/Prueba-e1640ac7.png" width="800px">


<p>Iniciamos el servidor web</p>

> sudo systemctl start nginx

<img alt="Prueba-8c9c58be.png" src="assets/Prueba-8c9c58be.png" width="800px">

<p>Restauramos  el servicio </p>

> sudo systemctl restart Nginx

<img alt="Prueba-e25421ba.png" src="assets/Prueba-e25421ba.png" width="800px">

<p>Recargamos la configuración de nginx</p>

> sudo systemctl reload Nginx

<img alt="Prueba-5e1585ae.png" src="assets/Prueba-5e1585ae.png" width="800px">

<p>Deshabilitamos el inicio automático de nginx, con el siguiente comando</p>

> sudo systemctl disable nginx

<img alt="Prueba-06f5eed5.png" src="assets/Prueba-06f5eed5.png" width="800px">

<p>Para habilitar el servicio automático, escribimos los siguiente </p>

> sudo systemctl enable nginx

<img alt="Prueba-c1a1eaf1.png" src="assets/Prueba-c1a1eaf1.png" width="800px">


***2.5 Configurar bloques de servidor***

<p>Creamos un directorio con el nombre de dominio que le hemos dado, usando el indicador -p para cualquier direcotrio principal, escribiendo..</p>

>   sudo mkdir -p /var/www/your_domain/html

<img alt="Prueba-3cc1b169.png" src="assets/Prueba-3cc1b169.png" width="800px">

<p>Luego asisnamos la propiedad del directorio con la variable de entorno $USER, con el comando..</p>

>  sudo chown -R $USER:$USER /var/www/your_domain/html

<p>Permitimos al propietario leer, escribir y ejecutar archivos, concediendo solo permisos de lectura y ejecución a los grupos y terceros, con el siguiente comando</p>

>  sudo chmod -R 755 /var/www/your_domain

<img alt="Prueba-ba349fbb.png" src="assets/Prueba-ba349fbb.png" width="800px">

<p>A continuación, cree una página de ejemplo index.html utilizando nano, escribiendo...</p>

>  nano /var/www/your_domain/html/index.html

<p>Escribiendo lo siguiente</p>



<p>Crearemos un bloque de servidor con las directivas correctas, escribiendo lo siguiente </p>

>  sudo nano /etc/nginx/sites-available/your_domain

<p>Escribiremos lo siguiente </p>


<p>Habilitaremos  el archivo creando un enlace entre él y el directorio sites-enabled, en el cual Nginx obtiene lecturas durante el inicio, con el siguiente comando</p>

>  sudo ln -s /etc/nginx/sites-available/your_domain /etc/nginx/sites-enabled/

<p>Para evitar un problema de memoria de depósito de hash que pueda surgir al agregar nombres de servidor, es necesario aplicar ajustes a un valor en el archivo /etc/nginx/nginx.conf, escribiendo...</p>

>   sudo nano /etc/nginx/nginx.conf

<p>Encuentre la directiva server_names_hash_bucket_size y borre el símbolo # para eliminar el comentario de la línea, escribiendo...</p>

<p>Ruta</p>

>  /etc/nginx/nginx.conf

<p>Copiamos los siguiente</p>

> http {
   ...
   server_names_hash_bucket_size 64;
   ...
 }
 ...

<p>Comprobamos que no hay errores de sintaxis con el siguiente comando,,,</p>

> sudo nginx -t

<p>Reiniciamos nginx para habilitar los cambios </p>

>  sudo systemctl restart nginx
