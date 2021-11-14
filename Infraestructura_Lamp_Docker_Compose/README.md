<img alt="README-1ac3d795.png" src="assets/README-1ac3d795.png" width="" height="" >

<br/>
<hr/>

# Índice #

## 1. Práctica de una pila LAMP ##

## 2. Servidor web ##

<hr/>

**1. Práctica de una pila LAMP**

<p>Una pila es un conjunto de servicios o paquetes instalables y que se relacionan entre si. En el siguiente diagrama se puede observar una pila LAMP (GNU/Linux, Apache, MySQL y PHP).</p>

<img alt="README-43bdbec3.png" src="assets/README-43bdbec3.png" width="800px"/>

**2. Servidor web**

<p>A continuación vamos a crear una estructura con 3 contenedores que conforman un sistema distribuido, interconectados entre si. Cada contenedor tiene servicios distintos que hará que la pila LAMP se constituye por medio de una red local.</p>

***Servidor web***

  - Nombre del contenedor: **www**
  - Puerto: **80**

***Servidor de BBDD***

  - Nombre del contenedor: **db**
  - Puerto: **3306**

***Servidor del sistema gestor de base de datos gráfico***

  - Nombre del contenedor: **phpmyadmin**
  - Puerto: **8000**

<hr/>

<p>Abriremos nuestro editor de código en nuestro caso VSCODE, y crearemos un nuevo proyecto, con la siguiente estructura de carpetas, como se muestra en la siguiente imagen</p>

<img alt="README-3a9e1831.png" src="assets/README-3a9e1831.png" width="300px" height="300px"/>

<p>Nos vamos al dichero **Dockerfile** , introducimos la versión **8.0.0 de phph con apache **</p>

<p>Seguidamente cambiaremos  la variable de entorno **DEBIAN_FRONTED** a modo no interactivo, que lo define para que los demás paquetes de instalación en consecuencia que soliciten una confirmación de algo en ejecución, lo omitan.</p>

<p>Las demás ejecuciones ya son para instalar extensiones de comunicación con docker, php y mysqli, así como las actualizaciones del repositorio de paquetes y por último la instalación de librerías y dependencias.</p>

<img alt="README-a8e1de0d.png" src="assets/README-a8e1de0d.png" width="800px"/>

<p>En el fichero de configuración **docker-compose.yml** configuraremos los siguientes servicios. En este punto, encontramos 3 bloques importantes donde se definen los servicios: **www, db y phpmyadmin**</p>

<img alt="README-156c7232.png" src="assets/README-156c7232.png" width="800px"/>

<p>Este es el .sql que se importa a **MySQL**</p>

<img alt="README-3bcd802f.png" src="assets/README-3bcd802f.png" width="800px"/>

<p>Este código php ubicado en **www/index.php** es para comprobar que el sitio carga bien y que existe correcta conectividad con la base de datos y que este puede dar lectura.</p>

<img alt="README-711c316c.png" src="assets/README-711c316c.png" width="800px"/>

<p>Ahora abriremos el terminal, listamos las carpetas de nuestra carpeta raíz, verificamos si se encuentra el proyecto creado, y entramos en la carpeta</p>

<img alt="README-2e56eec4.png" src="assets/README-2e56eec4.png" width="800px"/>

<p>Introduciremos el siguiente comando, que ejecuta la configuración de los contenedores en segundo plano</p>

<img alt="README-76ee1f61.png" src="assets/README-76ee1f61.png" width="800px"/>


<p>Los datos resultantes son de que se crean 3 contenedores, en principio con los prefijos docker-lamp_ que es el directorio donde se encuentra, procediendo a concatenar el nombre del contenedor y el sufijo _1 con resultado done.
<br/>
Para verificar los contenedores corriendo desde Docker Compose:
</p>

<img alt="README-e5cfb16c.png" src="assets/README-e5cfb16c.png" width="800px"/>

<p>Con esto bastará para hacer la prueba en un navegador y escribir **127.0.0.1**, equivalente a **127.0.0.1:80** o **localhost:80** con el puerto opcional.
</p>

<img alt="README-15fb196c.png" src="assets/README-15fb196c.png" width="800px"/>

<p>Se procede a realizar una consulta a la dirección 127.0.0.1:8000 para llegar al contenedor phpmyadmin. El usuario y la contraseña han sido definidos en el .yml.</p>

<img alt="README-2c7177c4.png" src="assets/README-2c7177c4.png" width="800px"/>

<p>Comprobamos que el acceso ha sido correcto, también verificamos que la base de datos se encuentra bien importada con su respectiva tabla y datos dentro, listo para ser gestionada.
</p>

<img alt="README-a0d74048.png" src="assets/README-a0d74048.png" width="800px"/>

<p>A partir de aquí, vamos a colocar el proyecto a trabajar, dentro del directorio www/, por ejemplo, si tu proyecto se llama app-servidor, lo revisarás en tu navegador como 127.0.0.1/app-servidor.</p>

<img alt="README-3a1dc51c.png" src="assets/README-3a1dc51c.png" width="800px"/>

<p>Para detener el stack con Docker Compose, es de esta manera:
</p>

>  docker-compose stop

<img alt="README-cf49102f.png" src="assets/README-cf49102f.png" width="800px"/>




<hr/>

Enlace github: <a href="https://github.com/joel92MM/Git/tree/main/Infraestructura_Lamp_Docker_Compose">enlace</a>
