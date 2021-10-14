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

<img src="" alt="">

<p>Para verificar la instalación de Maven en nuestro linux, utilizamos el siguiente comando: </p>

> mvn -version

<img src="" alt="">

<p>Aparecera una ventana similar a la siguiente</p>

<img src="" alt="">

***1.2 Construcción del proyecto***

<p>En el siguiente <a href="">enlace</a> esta disponible  el proyecto de una app en Java, donde haremos los siguientes cambios</p>

*<p>En el fichero web.xml, sustituiremos: </p>

>   <display-name  app-web-alumno</display-name  

<img src="" alt="">


* <p>por lo siguiente</p>

> display-name>app-web-aron</display-name

<img src="" alt="">


<p>donde aron seria nuestro nombre de alumno.</p>

*<p>En el fichero index.jsp, sustituiremos el valor de alumno siguiendo los mismos pasos que con el fichero anterior: </p>



<p>Lanzamos el siguiente comando: </p>

> mvn clean install

<img src="" alt="">


![image](https://user-images.githubusercontent.com/73592097/137400637-e42bfff8-9429-4586-a8aa-d4a873d8f613.png)


![image](https://user-images.githubusercontent.com/73592097/137400364-16219844-7d02-4ffb-a896-e2172e6fc16e.png)
