<img alt="README-d161c099.png" src="assets/README-d161c099.png" width="800px">
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

**3. PHP para Apache**

<p> Si usas Apache como servicio web, el paquete que necesitas será libapache2-mod-php</p>

>  sudo apt install -y php

**4. PHP para Nginx**

<p>Si usas Nginx, el paquete que necesitas es php-fpm</p>

> sudo apt install -y php-fpm


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

<p>Recargamos la configuracion de Nginx</p>

>sudo systemctl reload nginx 

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
