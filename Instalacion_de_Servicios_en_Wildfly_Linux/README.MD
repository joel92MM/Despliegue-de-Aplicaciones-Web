

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

<img src="" alt="carpeta tmp" width="800px"/>

<p>En mi git tenéis disponible la carpeta de los proyectos para descargar o clonar , en esta <a href="https://github.com/joel92MM/Git/tree/main/Instalacion_de_Servicios_en_Wildfly_Linux/quickstart-main">url</a>.</p>



***2.2 Instalación de Servicio Hello-RS***

<p>Accederemos al directorio helloworld-rs, desde la terminal y ejecutamos el siguiente comando..</p>

> mvn clean install


<img src="" alt="mvn clean" width="800px"/>

<p>Finalizara con un mensaje como el siguiente</p>

<img src="" alt="finalización" width="800px"/>

<p>Finalizada la compilación del proyecto acudiremos a wildfly, al apartado <strong>deployments</strong>, vamos a la pestaña <strong>+</strong>,

<img src="" alt="finalización" width="800px"/>


 <p>Seleccionamos la carpeta donde se encuentra nuestro proyecto. En concreto la ruta, donde se encuentra el archivo helloworld-rs.war</p>

 <img src="" alt="finalización" width="800px"/>


<p>Posteriormente pulsamos en el botón siguiente</p>

<img src="" alt="finalización" width="800px"/>


<p>En la siguiente ventana, dejamos las opciones como están y continuamos</p>

<img src="" alt="finalización" width="800px"/>


<p>Finalizará con un mensaje similar al siguiente</p>

<img src="" alt="finalización" width="800px"/>





<p>Una vez desplegado el Servicio, abrimos el navegador y en la url ponemos nuestra<strong> ip:puerto/helloworld-rs</strong>, y verificamos que se muestra como en las ventanas siguientes.</p>





***2.3 Instalación de Servicio Hello-WS***

<img src="" alt="desplegado wildfly" width="800px"/>
