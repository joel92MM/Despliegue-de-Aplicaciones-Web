<img alt="README-312dac96.png" src="assets/README-312dac96.png" width="800px"/>

# Índice #

## 1. Descarga de la imagen del docker Wildfly. ##



<hr/>
<br/>

**1. Descarga de la imagen del Docker Wildfly**

<p>Este paso es opcional ya que al construir nuestra imagen basada en el fichero Dockerfile se descargará la imagen base si no la tenemos en nuestro repositorio. Vamos a descargar en concreto la versión 25.0.0.Final de la imagen oficial. Para ello, vamos a utilizar el tag correspondiente:</p>

>   sudo docker pull jboss/wildfly:25.0.0.Final

<p>Obtendremos un mensaje como el siguiente</p>

<img alt="README-240d3de9.png" src="assets/README-240d3de9.png" width="800px"/>

<p>Veremos el listado de imagenes descargadas con el siguiente comando</p>

> sudo docker images

<img alt="README-dae8b23f.png" src="assets/README-dae8b23f.png" width="800px"/>

<p>Arrancamos un contenedor con la imagen y comprobamos que esta disponible el servidor de aplicaciones</p>

>sudo docker run -d -p 5000:8080 --name "servidor-desa" jboss/wildfly

<p>Donde (ver diagrama abajo):

+ -d (daemon) → arranca el servidor en background <br/>
-p 5000:8080 → publica el puerto 8080 de Wildfly al puerto 5000 del host (en nuestro caso el host es nuestro equipo)<br/>
--name “servidor-desa” → define un alias para el contenedor <br/>
+ c1bd… → es el código del contenedor (el hostname dentro de Docker)<br/></p>

<img alt="README-76ee09ae.png" src="assets/README-76ee09ae.png" width="800px"/>

<p>Con el siguietne comando veremos que docker a creado una nueva red</p>

>ip a

<img alt="README-f04de4fe.png" src="assets/README-f04de4fe.png" width="800px"/>

<hr/>

# Problemas que podemos encontrarnos #

<p>Si no hemos equivocado al asignar el puerto y queremos eliminar el contenedor de la imagen hacemos lo siguiente: </p>

<p>Primero listamos los contenedores que estan en ejecucion</p>

<img alt="README-ab25bb94.png" src="assets/README-ab25bb94.png" width="800px"/>

<p>Luego paramos el contenedor introduciendo el ID</p>

<img alt="README-b517d7ad.png" src="assets/README-b517d7ad.png" width="800px"/>

<p>Por ultimo eliminamos el contenedor dejando el puerto libre</p>

<img alt="README-9fc2af6d.png" src="assets/README-9fc2af6d.png" width="800px"/>

<p>Volvemos a listar los contenedores y veremos que hemos eliminado el deseado</p>

<img alt="README-76e3d829.png" src="assets/README-76e3d829.png" width="800px"/>

<hr/>

<p>Accediendo a la IP:puerto podemos ver la instalación</p>

<img alt="README-58fe6f7e.png" src="assets/README-58fe6f7e.png" width="800px"/>

<hr/>

Enlace github: <a href="https://github.com/joel92MM/Git/tree/main/Instalacion_Wildfly_en_Docker">enlace</a>
