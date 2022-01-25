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

<img alt="README-f91ecc6b.png" src="assets/README-f91ecc6b.png" width="800px"/>
<br/>
<br/>

<img alt="README-1dfb175b.png" src="assets/README-1dfb175b.png" width="800px"/>
<br/>
<br/>

<p>Clonamos el proyecto en local con el siguiente comando..</p>

> git clone [url_repositorio]

<img alt="README-b9c2eaa1.png" src="assets/README-b9c2eaa1.png" width="800px"/>
<br/>
<br/>

<p>Creamos la carpeta src, añadimos dentro un fichero index.php, que contenga contenido en el lenguaje php y una imagen personalizada con nuestro nombre.</p>

<img alt="README-383fb3b5.png" src="assets/README-383fb3b5.png" width="800px"/>
<br/>
<br/>

<p>Creamos el fichero Dockerfile. Incluye el siguiente contenido</p>

> FROM php:IMAGEN OFICIAL DE PHP<br/>
> COPY src/ /var/www/html <br/>
> EXPOSE 80

<img alt="README-2668e334.png" src="assets/README-2668e334.png" width="800px"/>
<br/>
<br/>

**3. Creación de el Pipeline**

<p>Creamos el fichero Jenkinfile, que tenga como misión realizar el despliegue. Tiene que tener acciones similares a las siguientes...</p>

> git clone this repository
> sudo docker build -t hello-word-php-apache
> sudo docker run -p 80:80 hello-word-php-apache

<img alt="README-fa82d2ba.png" src="assets/README-fa82d2ba.png" width="800px"/>
<br/>
<br/>

<p>Realizamos un push con todos los cambios.</p>

<img alt="README-36acb2d3.png" src="assets/README-36acb2d3.png" width="800px"/>
<br/>
<br/>

<img alt="README-1d20b9a6.png" src="assets/README-1d20b9a6.png" width="800px"/>
<br/>
<br/>

<p>Creamos una nueva tarea Pipeline</p>

<img alt="README-279fedc5.png" src="assets/README-279fedc5.png" width="800px"/>
<br/>
<br/>

<p>Luego nos vamos a la seccion pipeline, en la pestaña definicion cambiamos el valor y en la de SCM tambien a como se muestra en la siguiente imagen</p>

<img alt="README-07325424.png" src="assets/README-07325424.png" width="800px"/>
<br/>
<br/>

<p>Luegos sincronizamos la cuenta de github</p>

<img alt="README-6b817c8b.png" src="assets/README-6b817c8b.png" width="800px"/>
<br/>
<br/>

<p>En la pestaña añadir, añadimos las credenciales de nuestro github, usuario y contraseña</p>

<img alt="README-b491f85c.png" src="assets/README-b491f85c.png" width="800px"/>
<br/>
<br/>

<img alt="README-3ca6d487.png" src="assets/README-3ca6d487.png" width="800px"/>
<br/>
<br/>

<p>Modificamos los siguientes valores en las pestañas como se muestra en la imagen</p>

<img alt="README-28eb6a67.png" src="assets/README-28eb6a67.png" width="800px"/>
<br/>
<br/>

<img alt="README-1c30304f.png" src="assets/README-1c30304f.png" width="800px"/>
<br/>
<br/>


<p>Se nos muestra el pipeline solo falta construirlo</p>

<img alt="README-f4980c2d.png" src="assets/README-f4980c2d.png" width="800px"/>
<br/>
<br/>

<p>Ejecutamos el Pipeline</p>

<img alt="README-ea36e6b8.png" src="assets/README-ea36e6b8.png" width="800px"/>
<br/>
<br/>

<p>Comprobamos el estado </p>

<img alt="README-bad2922b.png" src="assets/README-bad2922b.png" width="800px"/>
<br/>
<br/>


<p>verificamos que se ha realizado de forma correcta visualizando el navegador.</p>

<img alt="README-148e7854.png" src="assets/README-148e7854.png" width="800px"/>
<br/>
<br/>

<img alt="README-a4629a08.png" src="assets/README-a4629a08.png" width="800px"/>
<br/>
<br/>

<p></p>
<p></p>



<hr/>

Enlace github: <a href="https://github.com/joel92MM/Git/tree/main/2ºTrimestre/ConfiguracionPipelinePHP">enlace</a>
