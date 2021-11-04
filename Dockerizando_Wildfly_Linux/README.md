<img alt="README-3679ff9e.png" src="assets/README-3679ff9e.png" width="800px"/>

<hr/>
<br/>

## 1. Creación del fichero dockerfile para Wildfly. ##

<hr/>

<p>Creamos el directorio de trabajo, con el siguiente comando: </p>

>  mkdir wildfly-config
  cd wildfly-config

<img alt="README-c4f08959.png" src="assets/README-c4f08959.png" width="800px"/>

<p>Creamos el fichero de configuración, con el siguiente comando: </p>

>  nano Dockerfile

<p>Añadimos la configuración de nuestra imagen </p>

<p>
# Base image
FROM jboss/wildfly:25.0.0.Final
<br/>
# Maintainer
MAINTAINER "jpexposito" "mail@example.com"
<br/>
# Create user admin with password admin
RUN /opt/jboss/wildfly/bin/add-user.sh admin admin --silent
<br/>
# Add custom configuration file
 <br/>
# ADD standalone.xml /opt/jboss/wildfly/standalone/configuration/
<br/>
# Add example.war to deployments
<br/>
# ADD example.war /opt/jboss/wildfly/standalone/deployments/
<br/>
# JBoss ports
EXPOSE 8080 9990 8009
<br/>
# Run
CMD ["/opt/jboss/wildfly/bin/standalone.sh", "-b", "0.0.0.0", "-bmanagement", "0.0.0.0", "-c", "standalone.xml"]
</p>

<img alt="README-16ae3368.png" src="assets/README-16ae3368.png" width="800px"/>

<p>Construcción de la imagen</p>

> sudo docker build -q --rm --tag=jboss/wildfly:25.0.0.Final-config .

<p>Obteniendo una salida similar a: </p>

<img alt="README-d58d7f11.png" src="assets/README-d58d7f11.png" width="800px"/>


<p>Verificamos que existe la imagen dentro de docker con el comando </p>

> sudo docker images

<img alt="README-5eb32730.png" src="assets/README-5eb32730.png" width="800px"/>

<p>Hemos construido nuestra primera imagen en docker</p>

## 2. Uso de la nueva imagen##

<hr/>

<p>Verificaremos que nuestra imagen se ejecuta con el comando</p>

>sudo docker run -d -p 8080:8080 -p 9990:9990 -p 8009:8009 --name servidor-wilfly-config -it jboss/wildfly:25.0.0.Final-config


<p>Teniendo en cuenta el parámetro --name servidor-wilfly-config que indica el nombre del servidor que hemos creado y arrancado, y que debe de ser significativo. Obtenemos, algo similar a:</p>

>f02cdd6962b18134ba34e6ba03331a65526c30fdcf3d961ac8d4817b7f0007e5

<img alt="README-059bfdb5.png" src="assets/README-059bfdb5.png" width="800px"/>


<p>Ahora verificaremos que el contenedor esta arrancado con el comando</p>

> sudo docker ps -a

<img alt="README-be011d9b.png" src="assets/README-be011d9b.png" width="800px"/>

<p>Accedemos a la consola de wildfly, y verificamos que se puede entrar en la consola de administración con el usuario admin.
</p>

<img alt="README-7586c30e.png" src="assets/README-7586c30e.png" width="800px"/>

<img alt="README-51fbfe86.png" src="assets/README-51fbfe86.png" width="800px"/>

<img alt="README-28165bd2.png" src="assets/README-28165bd2.png" width="800px"/>

<hr/>

Enlace github: <a href="https://github.com/joel92MM/Git/tree/main/Dockerizando_Wildfly_Linux">enlace</a>
