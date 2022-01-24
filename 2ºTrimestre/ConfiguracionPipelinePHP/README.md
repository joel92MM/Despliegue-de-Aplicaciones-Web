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
<p>Si no tenemos el proyecto en local, lo clonamos con el siguiente comando..</p>

> git clone [url_repositorio]

<p>Si lo tenemos clonado entramos en el repositorio y creamos la carpeta luego la iniciamos</p>

<img alt="README-1f6e1ee9.png" src="assets/README-1f6e1ee9.png" width="" height="" >

<p>Entramos dentro de la carpeta creada</p>

<img alt="README-46fd5b43.png" src="assets/README-46fd5b43.png" width="" height="" >

<p>Creamos la carpeta src </p>

<img alt="README-d7cfd2e6.png" src="assets/README-d7cfd2e6.png" width="" height="" >

<p>Añadimos dentro un fichero index.php, que contenga contenido en el lenguaje php y una imagen personalizada con nuestro nombre.</p>

<img alt="README-826f946e.png" src="assets/README-826f946e.png" width="" height="" >
<img alt="README-fbced398.png" src="assets/README-fbced398.png" width="" height="" >



<p>Volvemos a la raiz de nuestro proyecto.</p>

<img alt="README-a6c7daae.png" src="assets/README-a6c7daae.png" width="" height="" >
<p>Creamos el fichero Dockerfile. Incluye el siguiente contenido</p>

> FROM php:IMAGEN OFICIAL DE PHP<br/>
> COPY src/ /var/www/html <br/>
> EXPOSE 80

<img alt="README-dd99fef5.png" src="assets/README-dd99fef5.png" width="" height="" >

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

<p></p>
<p></p>

<p></p>


<hr/>

Enlace github: <a href="https://github.com/joel92MM/Git/tree/main/2ºTrimestre/ConfiguracionPipelinePHP">enlace</a>
