<img alt="README-6999de1f.png" src="assets/README-6999de1f.png" width="" height="" >


<br/>
<hr/>

# Índice #

## 1. Desplegar una aplicación ##

<hr/>

**1. Desplegar una aplicación**

<p>Utilizaremos una aplicación que se encuentra disponible en este <a href="https://github.com/joel92MM/Git/tree/main/Clusterizando_Servicio_Rest_Wildfly/helloworld-rs">enlace</a></p>

<p>Abriremos nuestro editor de código en nuestro caso VSCODE, y crearemos un nuevo proyecto, con la siguiente estructura de carpetas</p>

<img alt="README-ce565714.png" src="assets/README-ce565714.png" width="200px"/>

<p>En nuestra carpeta crearemos el archivo Dockerfile con el siguiente contenido de la imagen</p>

<img alt="README-aba05d3a.png" src="assets/README-aba05d3a.png" width="800px"/>

<p>Nos vamos al dichero **Dockerfile** , introducimos la versión **8.0.0 de phph con apache **</p>

<img alt="README-52dca979.png" src="assets/README-52dca979.png" width="800px"/>


<p>Este es el .sql que se importa a **MySQL**</p>

<img alt="README-95be10f6.png" src="assets/README-95be10f6.png" width="800px"/>

<p>En el fichero de configuración **docker-compose.yml** configuraremos los siguientes servicios. En este punto, encontramos 3 bloques importantes donde se definen los servicios: **www, db y phpmyadmin**</p>

<img alt="README-cd88406c.png" src="assets/README-cd88406c.png" width="800px"/>

<p>Una vez hecho esto crearemos el fichero war mediante el comando..</p>

> mvn clean install

<p>Construimos los contenedores</p>

<img alt="README-26f4c36f.png" src="assets/README-26f4c36f.png" width="800px"/>

<p>Listamos y comprobamos si los contenedores estan funcionando</p>

<img alt="README-fe748466.png" src="assets/README-fe748466.png" width="800px"/>

<p>Seguidamente para verificar que todo funcuona correctamente ejecutamos el siguiente comando </p>

> mvn clean jtty:run

<img alt="README-6a7aaffc.png" src="assets/README-6a7aaffc.png" width="800px"/>


<p>Accedemos al navegador para ver si los puertos estan funcionando</p>

<img alt="README-5fc0ebc5.png" src="assets/README-5fc0ebc5.png" width="800px"/>

<img alt="README-b0969acb.png" src="assets/README-b0969acb.png" width="800px"/>

<img alt="README-b52ea2e5.png" src="assets/README-b52ea2e5.png" width="800px"/>

<p>Comprobamos el acceso a phpmyadmin desde el puerto 8000</p>

<img alt="README-d05627b3.png" src="assets/README-d05627b3.png" width="800px"/>

<p>Finalmente el acceso a la aplicacion no se ejecuta</p>

<img alt="README-ffea55c2.png" src="assets/README-ffea55c2.png" width="800px"/>

<hr/>

Enlace github: <a href="https://github.com/joel92MM/Git/tree/main/Clusterizando_Servicio_Rest_Wildfly">enlace</a>
