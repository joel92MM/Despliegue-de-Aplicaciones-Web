**Editando**

<img src="https://user-images.githubusercontent.com/73592097/137165167-5fa8d67a-6d40-41f9-a67f-903ae9b88d87.png" alt="Portada">
<img src="https://user-images.githubusercontent.com/73592097/137165448-fd5d6cae-1e1b-4c42-8d38-fc0178073370.png" alt="Portada2">

<br/>
<hr/>

# Índice #


## 1. Creación de una app web en java. ##
* ### 1.1 Requisitos previos para la instalación ###
  * ###  Instalación de Java y Maven ###

* ### 1.2 Construcción del proyecto ###

<hr/>

**1. Requisitos  previos a la instalación**

***1.1 Instalación de Java y Maven***

<p>Dado que disponemos de Java de las instalaciones anteriores, ahora vamos a realizar la instalación de Maven </p>


****Instalación de Maven en linux****

<p>Para instalar Maven en Linux, hemos de escribir el comando siguiente: </p>

> sudo apt install maven

<img src="https://user-images.githubusercontent.com/73592097/137402135-8aea9841-9b08-4583-8179-60db90834a50.png" alt="Instalacion maven" width="800px">

<p>Para verificar la instalación de Maven en nuestro linux, utilizamos el siguiente comando: </p>

> mvn -version


<p>Aparecera una ventana similar a la siguiente</p>

<img src="https://user-images.githubusercontent.com/73592097/137402141-b0ea4ab6-3b52-48d1-9973-967d50030331.png" alt="Verificacion de maven" width="800px">


***1.2 Construcción del proyecto***

<p>En el siguiente <a href="">enlace</a> esta disponible  el proyecto de una app en Java, donde haremos los siguientes cambios</p>

* <p>En el fichero web.xml, sustituiremos: </p>

>   <display-name  app-web-alumno</display-name  

* <p>por lo siguiente</p>

> display-name>app-web-aron</display-name

<p>donde aron seria nuestro nombre de alumno.</p>

<img src="https://user-images.githubusercontent.com/73592097/137402149-4d85e1d5-d97b-40c9-a303-7dfea9209ef3.png" alt="Sustitucion de nombre" width="800px">

* <p>En el fichero index.jsp, sustituiremos el valor de alumno siguiendo los mismos pasos que con el fichero anterior: </p>


<img src="https://user-images.githubusercontent.com/73592097/137402142-99aa88ce-edf6-41ad-a99b-3b388a745de0.png" alt="Sustitucion fichero 2" width="800px">

* <p>Ahora modificaremos el fichero <strong>pom.xml</<strong> donde cambiaremos <strong>artifactld</<strong> y el  <strong>name</<strong> para poner el nombre nuestro </p>

 <img src="https://user-images.githubusercontent.com/73592097/137402145-a54e08db-f872-40a3-8df8-fcf57a15a4f3.png" alt="Sustitucion en pom" width="800px">

 * <p>También modificaremos el <strong>finalName</<strong> poniendo nuestro nombre</p>

 <img src="https://user-images.githubusercontent.com/73592097/137402146-923d9bab-ec69-4cf5-80a4-1995c531530d.png" alt="Sustitucion en finalName" width="800px">


* <p>Finalmente lanzamos el siguiente comando: </p>

> mvn clean install

<img src="" alt="Lanzando clean install" width="800px">

* <p>Acabara como la siguiente imagen</p>

<img src="" alt="" width="800px">


* <p> Seguidamente veremos una carpeta creada llamada target y dentro un paquete llamado war </p>

 <img src="https://user-images.githubusercontent.com/73592097/137402144-2f58b6e8-3c71-40e0-834f-6ec2c0458b2c.png" alt="Carpeta creada" width="800px">

* <p>Para finalizar debemos mover ese paquete a la carpeta webapps en la carpeta de instalación de tomcat</p>


<img src="https://user-images.githubusercontent.com/73592097/137402147-a4cd8128-691c-4786-92b2-df86f2b0d36a.png" alt="Mover paquete" width="800px">

 * <p>Abrimos el navegador con la direccion de apache-tomcat, en mi caso localhost:8083, no dirigimos a manager app, para nos va a pedir un usuario y contraseña, para configurarlo seria de la siguiente manera </p>

* <p>Nos dirigimos a la ruta de tomcat-users.xml, que esta en la carpeta de instalación, en mi caso seria la siguiente</p>

<img src="https://user-images.githubusercontent.com/73592097/137400637-e42bfff8-9429-4586-a8aa-d4a873d8f613.png" alt="" width="800px">

* <p>Entramos dentro, y pegamos el siguiente comando..</p>


<img src="https://user-images.githubusercontent.com/73592097/137400742-6c8c40f6-2efd-4335-8ff1-cf5510210790.png" alt="Comando a copiar" width="800px">


* <p>Volvemos a entrar con el usuario y contraseña, y una vez dentro del gestor de aplicaciones web de tomcat, veremos nuestra app-web-alumno ejecutandose</p>

<img src="https://user-images.githubusercontent.com/73592097/137400885-c6102764-83ee-4a3d-9ef7-71eaf8fe0819.png" alt="Gestor de aplicaciones tomcat" width="800px">


* <p>Pulsamos en la ruta y nos aparecera una ventana similar</p>

 <img src="https://user-images.githubusercontent.com/73592097/137400364-16219844-7d02-4ffb-a896-e2172e6fc16e.png" alt="Resultado de la app" width="800px">


 <hr/>

 Enlace github: <a href="https://github.com/joel92MM/Git/tree/main/Despliegue_War_Apache_Tomcat">enlace</a>
