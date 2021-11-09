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

<img alt="README-d50d4506.png" src="assets/README-d50d4506.png" width="800px"/>

<p>En el fichero <strong>index.jsp</strong> realizaremos el mismo procedimiento que en el punto anterior </p>

<img alt="README-2c537a49.png" src="assets/README-2c537a49.png" width="800px"/>

<p>En el pom sustituiremos el nombre alumno por nuestro nombre</p>

<img alt="README-65d1b67c.png" src="assets/README-65d1b67c.png" width="800px"/>

<p>Abriremos la terminal de VSCODE, y añadiremos los comandos que se muestran en la imagen para acceder al proyecto</p>

<img alt="README-c7df681d.png" src="assets/README-c7df681d.png" width="800px"/>

<p>Seguidamente lanzamos el siguiente comando</p>

> mvn clean install

<img alt="README-c9545444.png" src="assets/README-c9545444.png" width="800px"/>

<p>En la carpeta target veremos el war que nos a creado</p>

<img alt="README-04cac0fa.png" src="assets/README-04cac0fa.png" width="800px"/>

<p>Una vez construido el proyecto, podremos ver el resultado ejecutando en modo local el siguiente comando</p>

>mvn clean jetty:run

<img alt="README-fda66225.png" src="assets/README-fda66225.png" width="800px"/>

<p>Una vez terminada de ejecutar jetty podemos ver el resultado en nuestro navegador escribiendo lo siguiente</p>

> localhost:8082

<p>Nos mostrara un mensaje como el siguiente</p>

<img alt="README-283970bc.png" src="assets/README-283970bc.png" width="800px"/>

<p>Dentro de la carpeta de nuestra instalación debemos construir el dichero Dockerfile con el contenido siguiente: </p>

<p>
FROM jboss/wildfly<br/>

ARG WAR_FILE=target/*.war<br/>
##COPY ${JAR_FILE} app.jar<br/>

ADD ${ARG} /opt/jboss/wildfly/standalone/deployments/<br/>

ARG WILDFLY_NAME<br/>
ARG CLUSTER_PW<br/>

ENV WILDFLY_NAME=${WILDFLY_NAME}<br/>
ENV CLUSTER_PW=${CLUSTER_PW}<br/>

ENTRYPOINT /opt/jboss/wildfly/bin/standalone.sh -b=0.0.0.0 -bmanagement=0.0.0.0 -Djboss.server.default.config=standalone-full-ha.xml -Djboss.node.name=${WILDFLY_NAME} -Djava.net.preferIPv4Stack=true -Djgroups.bind_addr=$(hostname -i) -Djboss.messaging.cluster.password=${CLUSTER_PW}<br/>

</p>
<img alt="README-6442d388.png" src="assets/README-6442d388.png" width="800px"/>

<p>Seguidamente  el fichero .yml (docker-compose.yml) para la construcción del cluster con el siguiente contenido</p>
<p>
version: '3.5'<br/>
services:<br/>

  wildfly1:<br/>
    build:<br/>
      context: .<br/>
      args:<br/>
        WILDFLY_NAME: wildfly_1<br/>
        CLUSTER_PW: secret_password<br/>
    image: wildfly_1<br/>
    ports:<br/>
    - 8080:8080<br/>
    networks:<br/>
      wildfly_network:<br/>

  wildfly2:<br/>
    build:<br/>
      context: .<br/>
      args:<br/>
        WILDFLY_NAME: wildfly_2<br/>
        CLUSTER_PW: secret_password<br/>
    image: wildfly_2<br/>
    ports:<br/>
    - 8081:8080<br/>
    networks:<br/>
      wildfly_network:<br/>

networks:<br/>
  wildfly_network:<br/>
    ipam:<br/>
      driver: default<br/>

</p>
<img alt="README-05d3492a.png" src="assets/README-05d3492a.png" width="800px"/>
<p>
Observamos que existe:

Dos servidores WILDFLY (1/2).<br/>
Distintos puertos para el arraque de cada uno.<br/>
CLUSTER_PW: clave para la construcción del cluster.<br/>
networks: wildfly_network. Subred que estamos construyendo.<br/>
ipam: Configuración de la subred.<br/>
</p>

<p>Abriremos la carpeta Dockerfile y hacemos los siguiente</p>

<img alt="README-f67075b7.png" src="assets/README-f67075b7.png" width="800px"/>

<p>Posteriormente listaremos las imagenes con el comando </p>

>sudo docker-compose -a

<p>Y luego las borramos todas con el siguiente comando</p>

> sudo docker rmi $(sudo docker images -a -q) -f

<p>Ahora subiremos el war para desplegarlo en los dos puertos, con el comando </p>

> sudo docker-compose up --build

<img alt="README-10558f91.png" src="assets/README-10558f91.png" width="800px"/>


<p>Ahora tendremos desplegada la aplicación accesible a través del puerto 8081 </p>

<p>Puerto 8080</p>

<img alt="README-f9ea8196.png" src="assets/README-f9ea8196.png" width="800px"/>

<p>Puerto 8081</p>

<img alt="README-e51b92d1.png" src="assets/README-e51b92d1.png" width="800px"/>

<hr/>

Enlace github: <a href="https://github.com/joel92MM/Git/tree/main/Clusterizando_APP_Wildfly">enlace</a>
