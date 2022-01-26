<img alt="README-135cf7a1.png" src="assets/README-135cf7a1.png" width="" height="" >
<hr/>

# Índice #

## 1. Requisitos básicos ##

## 2. Creacion de repositorio ##

## 3. Ficheros de configuración ##

## 4. Creación pipeline en java ##

<hr/>

**1. Requisitos básicos**

- <p>Tener jenkins instalado</p>
- <p>Haber realizado el ejercicio del siguiente <a href="https://github.com/jpexposito/docencia/blob/master/DPL/ARQUITECTURAS/tareas/despliegue-jsp-apache-tomcat.md">enlace</a></p>

**2. Creación de repositorios**

<p>Creamos el repositorio</p>

<img alt="README-23fa61ab.png" src="assets/README-23fa61ab.png" width="" height="" >

<p>Paramos todos los contenedores de docker</p>

<img alt="README-9ec03bac.png" src="assets/README-9ec03bac.png" width="" height="" >

<p>Clonamos el proyecto del siguiente [enlace](https://github.com/jpexposito/docencia/blob/master/DPL/ARQUITECTURAS/tareas/despliegue-jsp-apache-tomcat.md).</p>

<img alt="README-cb8f9f0b.png" src="assets/README-cb8f9f0b.png" width="" height="" >




**3. Ficheros de configuración**

<p>Creamos nuestro DockerFile, con la siguiente estructura...</p>

>  FROM tomcat:version-seleccionada

>  LABEL maintainer="emailalumno@iespuerto.es"

>  ARG WAR_FILE=target/*.war

>  ADD ${WAR_FILE} /usr/local/tomcat/webapps/

>  EXPOSE 8082

>  CMD ["catalina.sh", "run"]</pre>


<img alt="README-8d7a8530.png" src="assets/README-8d7a8530.png" width="" height="" >

<p>Creamos el fichero Jenkinsfile, con el siguiente contenido...</p>

- State Test Junit. Debe de ejecutar el comando:

>  mvn clean test

- State Build. Debe de ejecutar el comando:

>  mvn clean package

- State Deploy. Debe de ejecutar el comando:

>  Sentencias Docker

- Test Integration. Debe de ejecutar el comando:

>  Verificar que la aplicación esta desplegada a través de un  (wget -m http://www.example.com).

> Verificar que el fichero descargado contiene el nombre del alumno.
 https://ubunlog.com/buscar-cadenas-o-patrones-texto-sin-formato/

<img alt="README-b57c3309.png" src="assets/README-b57c3309.png" width="" height="" >

<p>Creamos el target, con el siguiente comando</p>

> mvn clean install

<img alt="README-372ddbef.png" src="assets/README-372ddbef.png" width="" height="" >

<p>Quedaria una estructura similar a la siguiente </p>

<img alt="README-729cc6f4.png" src="assets/README-729cc6f4.png" width="" height="" >

<p>Subimos el proyecto a nuestro GitHub</p>

<img alt="README-be2ce045.png" src="assets/README-be2ce045.png" width="" height="" >

**4. Creación pipeline en java**

<p>En el Jenkis nos creamos una nueva tarea pipeline nueva</p>

<img alt="README-d638ad1a.png" src="assets/README-d638ad1a.png" width="" height="" >

<p>Luego le indicamos nuestro repositorio Git con las credenciales</p>

<img alt="README-4e4f0db0.png" src="assets/README-4e4f0db0.png" width="" height="" >

<br/>
<br/>
<img alt="README-0575d429.png" src="assets/README-0575d429.png" width="" height="" >

<p>Vemos el pipeline creado, lo ejecutamos</p>

<img alt="README-c9552211.png" src="assets/README-c9552211.png" width="" height="" >

<p>Vemos el proceso de construcción</p>

<img alt="README-9a3d75dd.png" src="assets/README-9a3d75dd.png" width="" height="" >

<p>Si nos da el siguiente mensaje de error</p>

<img alt="README-0ba2645b.png" src="assets/README-0ba2645b.png" width="" height="" >

<img alt="README-8c7667bf.png" src="assets/README-8c7667bf.png" width="" height="" >

<p>Nos iremos a la terminal y vemos los puertos ocupados</p>

<img alt="README-98709cbc.png" src="assets/README-98709cbc.png" width="" height="" >

<p>Vemos el contenedor que esta ocupando ese puerto </p>

<img alt="README-c3d1ac8f.png" src="assets/README-c3d1ac8f.png" width="" height="" >

<p>Luego paramos el contenedor</p>

<img alt="README-4a8e7606.png" src="assets/README-4a8e7606.png" width="" height="" >

<p>Volvemos a ejecutar el pipeline, y finalmente se ejecuta</p>

<img alt="README-7afc116a.png" src="assets/README-7afc116a.png" width="" height="" >

<p>La salida por consola es correcta</p>

<img alt="README-c2375645.png" src="assets/README-c2375645.png" width="" height="" >

<p>Si mostramos la direccion en el navegador, se mostraria el resultado siguiente</p>

<img alt="README-9bc1aec9.png" src="assets/README-9bc1aec9.png" width="" height="" >


<hr/>

Enlace github: <a href="https://github.com/joel92MM/Git/tree/main/2ºTrimestre/CreacionPipelineJava">enlace</a>
