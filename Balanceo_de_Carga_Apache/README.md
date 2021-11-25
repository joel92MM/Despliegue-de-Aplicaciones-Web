<img alt="README-3c4be5f2.png" src="assets/README-3c4be5f2.png" width="" height="" >
<br/>
<hr/>

# Índice #

## 1. Activacion de los modulos necesarios en Apache ##
## 2. Configuración de Apache para trabajar como balanceador de carga para el tráfico HTTP##

<hr/>





<hr/>

**1. Activacion de los modulos necesarios en Apache**

<p>Activamos los nodos ncesarios en apache, que son los de la siguiente imagen</p>

<p>Para desactivar un modulo es con el comando siguiente</p>

> a2dismod proxy_ajp

<p>Una vez realizado el paso anterior reiniciaremos el servicio Apache</p>

>   systemctl restart apache2

<img alt="README-f43e2928.png" src="assets/README-f43e2928.png" width="800px"/>

**2. Configuración de Apache para trabajar como balanceador de carga para el tráfico HTTP**

<p>Editamos el archivo 000-default.conf que está en el directorio /etc/apache2/sites-available:</p>

<p>Comprobamos el puerto apache</p>
<img alt="README-b9ab1870.png" src="assets/README-b9ab1870.png" width="800px"/>

<p>Añadimos las directivas Proxy y ProxyPass dentro de VirtualHost.</p>


<p>Tendremos que reemplazar IP-HTTP-SERVER-1, IP-HTTP-SERVER-2, IP-HTTP-SERVER-3, y IP-HTTP-SERVER-4, en nuestro caso deberá de ser localhost para las máquinas que estamos utilizando como Front-End</p>

<img alt="README-761bd70a.png" src="assets/README-761bd70a.png" width="800px"/>

<p>Utilizamos la app web de tareas anteriores, para crear una instancias de 4 nodos</p>

<p>El unico fichero que hay que modificar es docker-compose.yml</p>

<img alt="README-9b8e9f39.png" src="assets/README-9b8e9f39.png" width="800px"/>

<p>Luego haremos un mvn clean install para crearnos el war</p>
<p>Seguidamente eliminamos cualquier contenedor con el siguiente comando</p>

> docker-compose down

<p>Luego construimos las imagenes</p>

>docker-compose up --build

<img alt="README-4a689b5b.png" src="assets/README-4a689b5b.png" width="800px"/>

<p>Abrimos el navegador y lo probamos</p>

<img alt="README-3f19b284.png" src="assets/README-3f19b284.png" width="800px"/>

<img alt="README-17fce083.png" src="assets/README-17fce083.png" width="800px"/>

<img alt="README-603ad495.png" src="assets/README-603ad495.png" width="800px"/>

<img alt="README-b6414bd7.png" src="assets/README-b6414bd7.png" width="800px"/>

Enlace github: <a href="https://github.com/joel92MM/Git/tree/main/Balanceo_de_Carga_Apache">enlace</a>
