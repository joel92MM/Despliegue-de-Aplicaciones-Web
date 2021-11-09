<img alt="README-9a6e350a.png" src="assets/README-9a6e350a.png" width="800px"/>
<br/>
<hr/>

# Índice #

## 1. Instalación de Docker Compose ##

*  ## 1.1 Requisitos para instalar Docker Compose  ##

*  ## 1.2 Instalar Docker Compose en linux ##

## 2. Desplegando un Cluster de JBOSS con Docker ##

*  ## 2.1 Construcción del proyecto  ##

<hr/>

**1. Instalación de Docker Compose**

***1.1 Requisitos para instalar Docker Compose***

<p>Tener instalado Docker en nuestro sistema operativo</p>

***1.2 Instalar Docker Compose en Linux***

<p>Para descargar la versión estable actual de Docker Compose, ejecutamos el siguiente comando</p>

>  sudo curl -L "https://github.com/docker/compose/releases/download/1.29.2/docker-compose-$(uname -s)-$(uname -m)" -o /usr/local/bin/docker-compose

<img alt="README-8ea78324.png" src="assets/README-8ea78324.png" width="800px"/>

<p>Posteriormente aplicamos permisos ejecutables al archivo binario</p>

>  sudo chmod +x /usr/local/bin/docker-compose

<img alt="README-cfeb8e07.png" src="assets/README-cfeb8e07.png" width="800px"/>

<p>Seguidamente crearemos un enlace simbólico, con el siguiente comando</p>

>  sudo ln -s /usr/local/bin/docker-compose /usr/bin/docker-compose

<img alt="README-2def1c63.png" src="assets/README-2def1c63.png" width="800px"/>

<p>Para saber si tenemos Docker Compose instalado, ejecutaremos el siguiente comando</p>

> docker-compose --version

<img alt="README-64f92cdc.png" src="assets/README-64f92cdc.png" width="800px"/>

**2. Desplegando un Cluster de JBOSS con Docker**

<p>En el siguiente <a href="">enlace</a> dispones de un proyecto de una app en Java, donde debes de realizar los siguientes cambios:
</p>

<p>Abrimos el proyecto con un editor de codigo en nuestro caso VSCODE</p>

<p>En el fichero <strong>web.xml</strong> sustituiremos...</p>

>    <display-name>app-web-alumno</display-name>  

<p> donde alumno seria nuestro alumno </p>

<p>En el fichero <strong>index.jsp</strong> realizaremos el mismo procedimiento que en el punto anterior </p>
<p>Seguidamente lanzamos el siguiente comando</p>

> mvn clean install

<p></p>

<hr/>

Enlace github: <a href="https://github.com/joel92MM/Git/tree/main/Clusterizando_APP_Wildfly">enlace</a>
