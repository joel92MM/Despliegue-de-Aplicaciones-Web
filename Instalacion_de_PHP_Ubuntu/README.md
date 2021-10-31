<img alt="README-d161c099.png" src="assets/README-d161c099.png" width="800px"/>
<br/>
<br/>
<hr/>

# Índice #

## 1. Requisitos previos para la instalación ##

## 2. Como instalar PHP en Ubuntu 20.04 ##

## 3. PHP para Apache ##

## 4. PHP para Nginx ##

## 5. Como probar PHP en Ubuntu 20.04 ##

## 6. Configuración de subdominios ##

<hr/>

**1. Requisitos  previos a la instalación**

<p>Tener un S.O. Ubuntu 20.04 con un cuenta de superusuario no root. </p>

**2. Como instalar PHP en Ubuntu 20.04**

<p>Como de costumbre, actualizaremos la lista de paquetes</p>

> sudo apt update

<img alt="README-7f757927.png" src="assets/README-7f757927.png" width="800px"/>

**3. PHP para Apache**

<p> Si usas Apache como servicio web, el paquete que necesitas será libapache2-mod-php</p>

>  sudo apt install -y php

<img alt="README-6c90dbac.png" src="assets/README-6c90dbac.png" width="800px"/>

**4. PHP para Nginx**

<p>Si usas Nginx, el paquete que necesitas es php-fpm</p>

> sudo apt install -y php-fpm

<img alt="README-991ed243.png" src="assets/README-991ed243.png" width="800px"/>


<p>Será necesario configurar Nginx para conectar con el servicio PHP-FPM, editando su archivo de configuración, ya que PHP,se instala como servicio independiente</p>

>   sudo nano /etc/nginx/sites-available/default


<p>Buscamos esta sección: </p>

<p>...
        # pass PHP scripts to FastCGI server<br/>
        #<br/>
        #location ~ \.php$ {<br/>
        #       include snippets/fastcgi-php.conf;<br/>
        #<br/>
        #       # With php-fpm (or other unix sockets):<br/>
        #       fastcgi_pass unix:/var/run/php/php7.4-fpm.sock;<br/>
        #       # With php-cgi (or other tcp sockets):<br/>
        #       fastcgi_pass 127.0.0.1:9000;<br/>
        #}
...

</p>

<p>Activamos el bloque location con la configuración adecuada, en este caso correspondiente al servicio PHP-FPM:</p>

<p>...
        # pass PHP scripts to FastCGI server<br/>
        #<br/>
        location ~ \.php$ {<br/>
                include snippets/fastcgi-php.conf;<br/>
        #<br/>
        #       # With php-fpm (or other unix sockets):<br/>
                fastcgi_pass unix:/var/run/php/php7.4-fpm.sock;<br/>
        #       # With php-cgi (or other tcp sockets):<br/>
        #       fastcgi_pass 127.0.0.1:9000;<br/>
        }
...
</p>
<img alt="README-11084457.png" src="assets/README-11084457.png" width="800px"/>

<img alt="README-6cfa9392.png" src="assets/README-6cfa9392.png" width="800px"/>

<p>Recargamos la configuracion de Nginx</p>

>sudo systemctl reload nginx

<img alt="README-707ad6c9.png" src="assets/README-707ad6c9.png" width="800px"/>

<p>Para ver la version instalada de PHP o si esta instalado utilizamos...</p>

> php -v

<img alt="README-eb5ea5f0.png" src="assets/README-eb5ea5f0.png" width="800px"/>

**5. Como probar PHP en Ubuntu 20.04**

<p>Para probar PHP en Ubuntu 20.04 crearemos un pequeño archivo fácilmente accesible vía web</p>

>   sudo nano /var/www/html/info.php

<p>El contenido es el siguiente: </p>

<img alt="README-5bb49e6d.png" src="assets/README-5bb49e6d.png" width="800px"/>

<p>Ahora abriremos el navegador web e introducimos la siguiente direccion que se muestra en la imagen se vera una ventana similar</p>
<img alt="README-57292a5d.png" src="assets/README-57292a5d.png" width="800px"/>

**6. Configuración de subdominios**

<p>Copiaremos la pagina de php que hemos creado en la carpeta de subdominio de la práctica anterior, con el siguiente comando..</p>

> cp /var/www/html/info.php /var/www/ejemplojoel/html/

<img alt="README-9a84d611.png" src="assets/README-9a84d611.png" width="800px"/>

<p>Aplicaremos la misma configuracion al archivo de configuracion de subdominio ejemplojoel, como en la seccion anterior, con el comando...</p>

> nano /etc/nginx/sites-available/ejemplojoel

<p>Copiaremos el contenido en ese carpeta como se muestra en la imagen</p>

<img alt="README-3722ac6c.png" src="assets/README-3722ac6c.png" width="800px"/>

<p>Ahora recargamos el servicio nginx, con el comando</p>

> sudo systemctl reload nginx

<p>Posteriormente abriremos el navegador web e introducimos la direccion de nuestro servidor como se muestra en la imagen</p>

<img alt="README-a7461595.png" src="assets/README-a7461595.png" width="800px"/>

<p>Finalmente ya tendremos php instalado</p>

<hr/>

Enlace github: <a href="https://github.com/joel92MM/Git/tree/main/Instalacion_de_PHP_Ubuntu">enlace</a>
