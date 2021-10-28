

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

<img alt="Prueba-e85ec70a.png" src="assets/Prueba-e85ec70a.png" width="800px">

***2.2 Aplicar ajustes al firewall***

<p>Mostraremos un listado de los perfiles de la aplicación, con el siguiente comando..</p>

> sudo ufw app list

<p>Se mostrará un listado como el siguiente</p>

<img alt="Prueba-24700205.png" src="assets/Prueba-24700205.png" width="800px">

<p>Hanilitaremos el puerto, con el siguiente comando..</p>

> sudo ufw allow 'Nginx HTTP'

<img alt="Prueba-6fa4c862.png" src="assets/Prueba-6fa4c862.png" width="800px">

<p>Verificaremos el cambio con el siguiente comando </p>

> sudo ufw status

<img alt="Prueba-20b26419.png" src="assets/Prueba-20b26419.png" width="800px">


***2.3 Comprobar su servidor web***

<p>Ahora verificamos que el servicio esté en ejecución, con el siguiente comando..</p>

> systemctl status Nginx

<p>Nos mostrará los siguiente</p>

<img alt="Prueba-8182b175.png" src="assets/Prueba-8182b175.png" width="800px">

<p>Si queremos configurar un servidor que se encuentra en la nube escribimos..</p>

>   curl -4 icanhazip.com
<img alt="Prueba-2ab47d2e.png" src="assets/Prueba-2ab47d2e.png" width="800px">


<p>Luego copiamos la direccion ip en el navegador y se mostrara lo siguiente </p>

<img alt="Prueba-88d8e402.png" src="assets/Prueba-88d8e402.png" width="800px">


<p>El problema son los puertos para ello tenemos que ir a la siguiente carpeta y escribir un puerto libre en nuestro caso es 8085</p>

<p>Antes tendremos que darle permiso de escritura para cambiar los puertos con el comando que se muestra en la imagen </p>

<img alt="Prueba-b963fc06.png" src="assets/Prueba-b963fc06.png" width="800px">

<p>Ahora entramos en la carpeta para cambiar los puerto con el siguiente comando </p>

<img alt="Prueba-e1ed7e52.png" src="assets/Prueba-e1ed7e52.png" width="800px">

<p>Y procedemos a cambiar los puertos</p>

<img alt="Prueba-0f0cc8e3.png" src="assets/Prueba-0f0cc8e3.png" width="800px">

<p>Y como se muestra en la imagen estaria iniciado el servicio</p>

<img alt="Prueba-60f674a1.png" src="assets/Prueba-60f674a1.png" width="800px">

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

<img alt="Prueba-17dc7a83.png" src="assets/Prueba-17dc7a83.png" width="800px">

<p>Luego asisnamos la propiedad del directorio con la variable de entorno $USER, con el comando..</p>

>  sudo chown -R $USER:$USER /var/www/your_domain/html

<img alt="Prueba-50a0f841.png" src="assets/Prueba-50a0f841.png" width="800px">


<p>Permitimos al propietario leer, escribir y ejecutar archivos, concediendo solo permisos de lectura y ejecución a los grupos y terceros, con el siguiente comando</p>

>  sudo chmod -R 755 /var/www/your_domain

<img alt="Prueba-714df34f.png" src="assets/Prueba-714df34f.png" width="800px">

<p>A continuación, cree una página de ejemplo index.html utilizando nano, escribiendo...</p>

>  nano /var/www/your_domain/html/index.html

<img alt="Prueba-8eef718d.png" src="assets/Prueba-8eef718d.png" width="800px">

<p>Escribiendo lo siguiente</p>



<p>Crearemos un bloque de servidor con las directivas correctas, escribiendo lo siguiente </p>

>  sudo nano /etc/nginx/sites-available/your_domain

<p>Escribiremos lo siguiente </p>

<img alt="Prueba-566cf50e.png" src="assets/Prueba-566cf50e.png" width="800px">

<p>Habilitaremos  el archivo creando un enlace entre él y el directorio sites-enabled, en el cual Nginx obtiene lecturas durante el inicio, con el siguiente comando</p>

>  sudo ln -s /etc/nginx/sites-available/your_domain /etc/nginx/sites-enabled/

<img alt="Prueba-1797f7ea.png" src="assets/Prueba-1797f7ea.png" width="800px">

<p>Para evitar un problema de memoria de depósito de hash que pueda surgir al agregar nombres de servidor, es necesario aplicar ajustes a un valor en el archivo /etc/nginx/nginx.conf, escribiendo...</p>

>   sudo nano /etc/nginx/nginx.conf

<img alt="Prueba-fda5e78c.png" src="assets/Prueba-fda5e78c.png" width="800px">

<p>Encuentre la directiva server_names_hash_bucket_size y borre el símbolo # para eliminar el comentario de la línea, escribiendo...</p>

<p>Ruta</p>

>  /etc/nginx/nginx.conf

<p>Descomentamos la siguiente linea</p>

> http {
   ...
   server_names_hash_bucket_size 64;
   ...
 }
 ...

 <img alt="Prueba-f2eeeb92.png" src="assets/Prueba-f2eeeb92.png" width="800px">

<p>Comprobamos que no hay errores de sintaxis con el siguiente comando,,,</p>

> sudo nginx -t

<img alt="Prueba-efda3ab6.png" src="assets/Prueba-efda3ab6.png" width="800px">

<p>Reiniciamos nginx para habilitar los cambios </p>

>  sudo systemctl restart nginx

<img alt="Prueba-f1bc684a.png" src="assets/Prueba-f1bc684a.png" width="800px">

<hr/>

Enlace github: <a href="https://github.com/joel92MM/Git/tree/main/Instalacion_de_NGINX_LINUX">enlace</a>
