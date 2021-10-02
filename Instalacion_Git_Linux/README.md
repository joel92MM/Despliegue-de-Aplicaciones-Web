
<img src="https://user-images.githubusercontent.com/73592097/135716715-ce02a472-f9ea-4b01-be32-cc38e4e535cc.png" alt="Titulo imagen">

<hr/>


 


**Índice**

* Requisitos previos para la instalación.

* Instalación de Git con paquetes predeterminados.

* Instalación de Git desde la fuente.

* Configuración de Git.


<hr/>

<br/>


**1. Requisitos previos para la instalación**

> <p> Para la instalación de Git en linux, necesitarás un servidor Ubuntu 20.04 con una cuenta de superusuario, debidamente configurados.</p>

**2. Instalación de Git con paquetes predeterminados.**

<p>Arrancamos nuestro servidor Ubuntu, nos aparecerá la siguiente ventana.</p>


<img src="https://user-images.githubusercontent.com/73592097/135721463-e480cd2f-231b-4b71-96a9-1d5ca27b6a2f.png" alt="Muestra pantalla terminal de ubuntu">

<p>A continuación, iniciamos sesión en el servidor con el usuario y contraseña, que hemos configurado anteriormente…</p>


<img src="https://user-images.githubusercontent.com/73592097/135721611-2ac6315b-1363-4d40-a665-706a115b7db5.png" alt="inicio sesion">

<p>Previamente, accederemos a superusuario como el comando <strong>sudo -s</strong>, y la contraseña que hemos configurado al instalarlo…</p>


<img src="https://user-images.githubusercontent.com/73592097/135721656-d16172ef-2b66-458a-822e-e817b3bf5ed8.png" alt="Acceder a superusuario">


<p>Para saber si tenemos instalado Git en nuestro servidor, utilizaremos el siguiente comando:</p>

<img src="https://user-images.githubusercontent.com/73592097/135721691-42570526-15e6-408b-8b7f-2d95f6d81257.png" alt="instalacion git">

<p>En nuestro caso tenemos Git instalado, ahora procederemos a configurar Git, sin embargo, si no obtuviste el mismo resultado, te muestro los pasos a continuación….</p>

<img src="https://user-images.githubusercontent.com/73592097/135721700-066ee049-f854-4adf-8241-f4de892f6d5d.png" alt="Pasos no instalacion de git">

**3. Instalación de Git desde la fuente.**

<p>Este método es más flexible a la hora de instalar Git, también permite descargar la versión mas reciente, que puede brindar mas control sobre las opciones si quiere personalizarlo.</p>

<p>Para instalar el software necesario para Git, debemos actualizar nuestro índice local de paquetes, los comandos serian los siguientes…</p>

<img src="https://user-images.githubusercontent.com/73592097/135721702-bb05382f-bdfc-4033-943f-4618381e234a.png" alt="Actualizacion">
<br/>
<img src="https://user-images.githubusercontent.com/73592097/135721703-8a5dea4e-bc01-44d3-a018-a22486699799.png" alt="Actualizacion de indice">


<p>Seguidamente crearemos un directorio temporal, y luego entramos en el mismo, para descargar tarball de Git…</p>

<img src="https://user-images.githubusercontent.com/73592097/135721704-d084939a-e8b3-46db-8746-a44dd0eadab1.png" alt="Creacion de directorio">

<p>Ahora mismo estaremos apuntando a la carpeta creada tmp, todo lo que descargaremos estará en esa carpeta.</p>

<hr/>

<p>Para descargar la versión mas reciente de Git, accederemos a la lista tarball, y buscamos la versión mas reciente, en este caso es la 2.9.5, utilizaremos curl y enviaremos el archivo que descarguemos a git.tar.gz, a continuación, mostramos el proceso….</p>

<img src="https://user-images.githubusercontent.com/73592097/135721706-d8f68824-92aa-4066-b519-eb125cbcc41b.png" alt="Mostrando el proceso">

<p>Procederemos a descomprimir el archivo tarball</p>

<img src="https://user-images.githubusercontent.com/73592097/135721707-f65b155b-72a4-4113-aceb-1f239e2b47f5.png" alt="Descomprimir tarball">

<p>Ahora accederemos al nuevo directorio de Git…</p>

<img src="https://user-images.githubusercontent.com/73592097/135721708-c7ef7d2f-c0e7-4f69-8ad8-9424384e5f4e.png" alt="Accediendo al directorio Git">


<p>Luego vamos a crear el paquete para poder instalarlo con estos dos comandos que se muestran a continuación….</p>

<img src="https://user-images.githubusercontent.com/73592097/135721709-a62838ea-afd5-498d-9e6a-465c1bf10c3e.png" alt="creacion de paquete">
<br/>
<img src="https://user-images.githubusercontent.com/73592097/135721711-071de6c6-326b-4f94-b8ca-24e0ea811ac9.png" alt="Creacion de paquete volumen 2">


<p>Seguidamente sustituiremos el proceso de Shell para utilizar la versión de Git instalada con este comando….</p>

<img src="https://user-images.githubusercontent.com/73592097/135721712-4787780f-9756-42e8-b2db-56ea5b52600c.png" alt="Version de git">


<p>Finalmente, completada la instalación podemos comprobarlo, que se ha realizado correctamente, utilizando el comando….</p>

<img src="https://user-images.githubusercontent.com/73592097/135721713-81d584e8-0bb8-4c4e-afec-53cc41ec5fac.png" alt="Comprobar actualizacion">


**4. Configuración de Git**

<p>En este paso vamos a proceder a configurar Git, para que los mensajes de confirmación que genere contengan la información correcta y lo respalden a medida que compilamos nuestro proyecto de software.</p>
<p>Procederemos a configurar nuestro Git, con el comando **config,** tendremos que especificar nuestro nombre y dirección de correo electrónico, a continuación, mostraremos el proceso...</p>

<img src="https://user-images.githubusercontent.com/73592097/135723216-49c09000-c733-4f9f-b52c-42209a452620.png" alt="Confifuracion de Git">

<p>Si queremos ver los elementos de configuración anteriormente creados, introduciremos el comando **config - -list** y vemos el resultado a continuación…</p>

<img src="https://user-images.githubusercontent.com/73592097/135723218-0807ef5d-082b-468c-9909-fdcebf9a1509.png" alt="Configuracion anterior">

<p>Esta información se almacena en un archivo de configuración de Git, si queremos editarlos manualmente, utilizaremos unos de los editores de texto, en nuestro caso será el comando **nano**</p>

<img src="https://user-images.githubusercontent.com/73592097/135723219-503a9dec-9dd5-4b5d-a3ee-bc753a8209f0.png" alt="Editar archivos">

<p>El editor de texto se muestra a continuación...</p>

<img src="https://user-images.githubusercontent.com/73592097/135723221-40bb0e12-bfa7-4a07-8663-907b792f702d.png" alt="Editor de texto">

<p>Si has seguido todos estos pasos, deberás tener Git configurado en Ubuntu server.</p>

<hr/>

