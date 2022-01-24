<img alt="README-ef269f48.png" src="assets/README-ef269f48.png" width="" height="" >
<hr/>

# Índice #

## 1. Requisitos básicos ##

## 2. Creación de ficheros en GitHub ##

## 3. Creación de el Pipeline ##




<hr/>

**1. Requisitos básicos**

- <p>Tener jenkins instalado</p>

**2. Creación de ficheros en GitHub**

<p>Creamos un repositorio en nuestra cuenta de github, de nombre php-helloworld.</p>
<p>Clonamos el proyecto en local</p>
<p>Creamos la carpeta src. Añadimos dentro un fichero index.php, , que contenga contenido en el lenguaje php y una imagen personalizada con nuestro nombre.</p>
<p>Volvemos a la raiz de nuestro proyecto.</p>
<p>Creamos el fichero Dockerfile. Incluye el siguiente contenido</p>

> FROM php:IMAGEN OFICIAL DE PHP<br/>
> COPY src/ /var/www/html <br/>
> EXPOSE 80

**3. Creación de el Pipeline**

<p>Creamos el fichero Jenkinfile, que tenga como misión realizar el despliegue. Tiene que tener acciones similares a las siguientes...</p>

> git clone this repository
> sudo docker build -t hello-word-php-apache
> sudo docker run -p 80:80 hello-word-php-apache

<p>Realizamos un push con todos los cambios.</p>

<p>Creamos el Pipeline dentro de tu instalación de Jenkins.alumno, sincronizando desde tu cuenta de github (www.github.com/alumno/hello-word-php-apache.git) o similar.</p>

<p>Ejecutamos el Pipeline, y verificar que se ha realizado de forma correcta visualizando el navegador.</p>
<p></p>
<p></p>
v
<p></p>
<p></p>
v
<p></p>


<hr/>

Enlace github: <a href="https://github.com/joel92MM/Git/tree/main/2ºTrimestre/ConfiguracionPipelinePHP">enlace</a>
