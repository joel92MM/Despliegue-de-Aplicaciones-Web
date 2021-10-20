**Editando README**


# Índice #


<img src="https://user-images.githubusercontent.com/73592097/137773610-50ae3e6c-5bc5-48d2-9641-95f3e005e2e6.png" alt="portada">

## 1. Creando nuestro servicio restfulapi. ##

* ### 1.1 Requisitos previos para la instalación ###

* ### 1.2 Construcción del proyecto ###

## 2. Despliegue del servicio ##

* ### 2.1 Consumo del servicio ###
* ### 2.2. Problemas durante el despliegue ###
* ### 2.3. Mejoras en el servicio ###

<hr/>

**1. Creando nuestro servicio restfulapi**

***1.1 Requisitos previos***

<p>Dado que disponemos de Java de las instalaciones anteriores, y también de la instalación de Maven, nos vamos al paso siguiente </p>


***1.2 Construcción del proyecto***

<p>En el siguiente enlace, disponemos de un proyecto Java, <a href="https://github.com/jpexposito/docencia/tree/master/comun/ejemplos/java/rest-service">enlace</a></p>

<p>Crearemos el fichero .war</p>

<img src="https://user-images.githubusercontent.com/73592097/137990313-64c12022-d666-4b88-8746-86c625f0a458.png" alt="clean" width="800px">

<p>Realizamos las modificaciones en el fichero web.xml </p>

<img src="https://user-images.githubusercontent.com/73592097/137989879-24c80106-fe02-4b34-9af8-8707da21340c.png" alt="cambios fichero xml" width="800px">

<p>Movemos el paquete a la carpeta webapps  que se encuentra en la carpeta de instalacion de tomcat</p>

<img src="https://user-images.githubusercontent.com/73592097/137990644-5543a54e-a5a8-4186-83b1-3ce9e3a4288f.png" alt="target" width="800px">

**2. Despliegue del servicio**

<p>Siguiendo los pasos que la anterior tarea, desplegamos el servicio en nuestro servidor de aplicaciones Tomcat</p>
<img src="https://user-images.githubusercontent.com/73592097/137811793-624e3fbe-dd98-46e8-a67d-a33af7e7e1e8.png" alt="servidor de aplicaciones" width="800px">

<p>Comprobamos si la aplicacion se ejecuta</p>

![](assets/README-6f9b32c6.png)

***2.1 Consumo del servicio***

<p>Nos descargaremos un cliente rest, desde este <a href="https://install.advancedrestclient.com/install">enlace</a>.</p>

<img src="https://user-images.githubusercontent.com/73592097/137811807-2e0dc042-0e1a-45c8-b570-6e07840c2678.png" alt="descarga cliente rest" width="800px">



<p>Vamos a la carpeta de logs para buscar el error</p>


<img src="https://user-images.githubusercontent.com/73592097/137993260-eca478d0-f1a4-46c8-9f54-844799795b7a.png" alt="logs" width="800px">

<p>Desde la siguiente  <a href="https://eclipse-ee4j.github.io/jersey/download.html"> url, </a>descargamos la libreria, luego la descomprimimos </p>

![](assets/README-4cf13235.png)


<p>Luego copiamos todos los archivos .jar dentro de la carpeta WEB-INFO/lib</p>

![](assets/README-f61968bb.png)

<p>Consulto la pagina de logs, y el error sigue</p>

![](assets/README-0737d0f0.png)
