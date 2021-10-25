

<img src="https://user-images.githubusercontent.com/73592097/138740657-9133b3d1-6f36-4be5-a09d-bcfd79276043.png" alt="portada" width="800px">
<br/>
<hr/>

# Índice #

## 1. Requisitos previos para la instalación ##

*  ## 1.1 Instalación de Java, Maven y WildFly ##


## 2. Pasos para realizar la instalación de los servicios rest/ws en wildfly ##

*  ## 2.1 Descarga de los ejemplos ##

*  ## 2.2 Instalación de Servicio Hello-RS ##

*  ## 2.3 Instalación de Servicio Hello-WS ##


<hr/>

**1. Requisitos  previos a la instalación**

<p>Tener un S.O. Ubuntu 20.04 con un cuenta de superusuario no root. También es necesario disponer de Java instalado y Maven.</p>



***1.1 Instalación de Java, Maven y WildFly***
<p>Prioritariamente tenemos que tener instalado Java y Maven en nuestro equipo, para asegurarnos ejecutaremos los siguientes comandos que les muestro a continuación: </p>

> java --version

<img src="https://user-images.githubusercontent.com/73592097/138179714-6e2d3432-a607-44c4-a811-993b02f6de96.png" alt="versión de maven" width="800px">

<br/>

> mvn -version

<img src="https://user-images.githubusercontent.com/73592097/138179719-3f36224c-9360-43c9-b20d-fa0ba55dcc90.png" alt="versión de java" width="800px">

<p>Además tener desplegado el servidor de aplicaciones WildFly, como se muestra a continuación...</p>


<img src="https://user-images.githubusercontent.com/73592097/138314894-ba280454-4a4f-4b7e-a17e-fbc939b07e86.png" alt="acceso por navegador" width="800px">

**2. Pasos para realizar la instalación de los servicios res/ws en WildFly**

***2.1 Descarga de los ejemplos***

<p>Abriremos una terminal, nos dirigimos a la carpeta tmp, y ahí, ponemos la carpeta que vamos a descargar a continuación</p>

> cd /tmp

<img src="https://user-images.githubusercontent.com/73592097/138779506-5138a869-205b-4f31-a0a9-0680581af681.GIF" alt="carpeta tmp" width="800px"/>

<p>En mi git tenéis disponible la carpeta de los proyectos para descargar o clonar , en esta <a href="https://github.com/joel92MM/Git/tree/main/Instalacion_de_Servicios_en_Wildfly_Linux/quickstart-main">url</a>.</p>



***2.2 Instalación de Servicio Hello-RS***

<p>Accederemos al directorio helloworld-rs</p>
<img src="https://user-images.githubusercontent.com/73592097/138779486-c51b39d7-ac42-47b6-8f8a-0a0b7cce7c00.GIF" alt="carpeta tmp" width="800px"/>
<img src="https://user-images.githubusercontent.com/73592097/138779487-2ddf6f70-ccbb-44fb-9776-260ffbf4926b.GIF" alt="mvn clean" width="800px"/>


<p>y  desde la terminal y ejecutamos el siguiente comando..</p>

> mvn clean install


<img src="https://user-images.githubusercontent.com/73592097/138779488-bf2f0e81-ff7e-496e-b777-769cad139533.GIF" alt="mvn clean" width="800px"/>

<p>Finalizara con un mensaje como el siguiente</p>

<img src="https://user-images.githubusercontent.com/73592097/138779490-ccde4d77-2383-4f30-bc56-315906b96de8.GIF" alt="finalización" width="800px"/>

<p>Finalizada la compilación del proyecto acudiremos a wildfly, al apartado <strong>deployments</strong>, vamos a la pestaña <strong>+</strong> y luego elegimos la primera opción</p>


<img src="https://user-images.githubusercontent.com/73592097/138780472-93983db6-06fb-40a4-930f-d483f9f5564c.GIF" alt="finalización" width="800px"/>


 <p>Seleccionamos la carpeta donde se encuentra nuestro proyecto. En concreto la ruta, donde se encuentra el archivo helloworld-rs.war</p>

 <img src="https://user-images.githubusercontent.com/73592097/138779499-ed04b561-25ac-4a2b-9c1f-8f0cc54ad8dd.GIF" alt="finalización" width="800px"/>


<p>Posteriormente pulsamos en el botón siguiente</p>

<p>En la siguiente ventana, dejamos las opciones como están y continuamos</p>

<img src="https://user-images.githubusercontent.com/73592097/138779500-159f5dde-3147-4d96-a30d-6d96ecbd6e39.GIF" alt="finalización" width="800px"/>


<p>Finalizará con un mensaje similar al siguiente</p>

<img src="https://user-images.githubusercontent.com/73592097/138779502-10180cab-7bba-47e6-a794-734c2f25dee4.GIF" alt="finalización" width="800px"/>



<p>Una vez desplegado el Servicio, abrimos el navegador y en la url ponemos nuestra<strong> ip:puerto/helloworld-rs</strong>, y verificamos que se muestra como en las ventanas siguientes.</p>


<img src="https://user-images.githubusercontent.com/73592097/138779503-cae88cb5-7672-473b-aa89-a441303976c4.GIF" alt="finalización" width="800px"/>

<img src="https://user-images.githubusercontent.com/73592097/138779504-4aee4ad9-c95c-4b1d-9cb4-d1e76a704ae8.GIF" alt="finalización" width="800px"/>

<img src="https://user-images.githubusercontent.com/73592097/138779505-453b9bdb-4375-412c-94bd-694abb6280ac.GIF" alt="finalización" width="800px"/>





***2.3 Instalación de Servicio Hello-WS***

<p>Ahora vamos a instalar el siguiente servicio, que será como en los pasos anteriores</p>

<p>Accederemos al directorio hello-ws, para posteriormente ejecutar el siguiente comando</p>

> mvn clean install

<img src="https://user-images.githubusercontent.com/73592097/138779493-21035af1-6f60-497f-b54a-1c854be53f06.GIF" alt="mvn clean install" width="800px"/>

<p>Hasta finalizar con un mensaje similar al siguiente</p>

<img src="https://user-images.githubusercontent.com/73592097/138779496-b1199cf8-a67c-4e12-b97b-604ff5f48493.GIF" alt="finalizacion" width="800px"/>

<p>Hacemos los mismos pasos para desplegar el servicio que en el paso anterior</p>

<p>Una vez desplegado el servicio, lo verificaremos en nuestro servidor , introduciendo en la url lo siguiente <strong> ip:puerto/helloworld-ws</strong> </p>

<p>Nos mostrará un mensaje similar al siguiente</p>

<img src="https://user-images.githubusercontent.com/73592097/138779498-aa97d0da-b2a9-4eef-9c99-e084de010f0c.GIF" alt="mensaje" width="800px"/>

<hr/>

Enlace github: <a href="https://github.com/joel92MM/Git/tree/main/Instalacion_de_Servicios_en_Wildfly_Linux">enlace</a>
