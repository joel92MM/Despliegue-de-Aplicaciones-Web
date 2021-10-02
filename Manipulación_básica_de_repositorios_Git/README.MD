

<img src="https://user-images.githubusercontent.com/73592097/135724369-bd91d9fb-a636-420b-9adb-48374b8c25a0.png" alt="Portada imagen">

<br/>
<hr/>

**Índice**

* Requisitos previos para la manipulación de repositorios en Git. 

* Configuración de Git.

* Creación de un repositorio.

* Comprobar el estado del repositorio.

  + Comprobar el estado del repositorio.

  + Crear un fichero indice.txt con el siguiente contenido:

    + Capítulo 1: Instalación de Git por el alumno XXX (donde XXX es el nombre del alumno)

    + Capítulo 2: Flujo de trabajo básico

  + Comprobar de nuevo el estado del repositorio.

  + Añadir el fichero a la zona de intercambio temporal.

  + Volver a comprobar una vez más el estado del repositorio.

* Realizando commit´s.

* Modificación de ficheros.

  + Cambiar el fichero indice.txt para que contenga lo siguiente:

    + Capítulo 1: Instalación de Git por el alumno XXX (donde XXX es el nombre del alumno)
    + Capítulo 2: Flujo de trabajo básico
    + Capítulo 3: Gestión de ramas
    + Capítulo 4: Repositorios remotos
  + Mostrar los cambios con respecto a la última versión guardada en el repositorio.
  + Hacer un commit de los cambios con el mensaje **Añadido los capítulos 3 y 4.**
  
* Historial de Git.

  + Mostrar los cambios de la última versión del repositorio con respecto a la anterior.

  + Cambiar el mensaje del último commit por **Añadido el capitulo sobre gestión de ramas al índice.**

  + Volver a mostrar los últimos cambios del repositorio.

<br/>
<hr/>





**1. Requisitos previos para la manipulación de repositorios en Git.**

<p>Para la manipulación de repositorios en Git, tenemos que disponer de una distribución Linux, así como anteriormente haber realizado los pasos de instalación y configuración de Git en Ubuntu Server.</p>

**2. Configuración de Git**

<p>Accederemos a nuestro Ubuntu Server, introducimos el login, con su correspondiente contraseña, para acceder a root...</p>
<img src="https://user-images.githubusercontent.com/73592097/135724316-eb7130c9-5625-42ec-8e5c-bd20f9286f16.png" alt="Logeando en ubuntu">
<p>Una vez en root, accederemos a superusuario como se describe a continuación…</p>
<img src="https://user-images.githubusercontent.com/73592097/135724317-858c0fb0-1cf1-4329-abb7-bc5c7b81f1ce.png" alt="Acceder como superusuario">
<p>En este apartado vamos a configurar el nombre de usuario, correo electrónico y activar el coloreado de salida en Git, usando los comandos que veremos a continuación, con su correspondiente resultado final.</p>
<img src="https://user-images.githubusercontent.com/73592097/135724318-21b13d90-5f13-4be8-b8b2-3965c0773768.png" alt="Configuracion de usuario">

**3. Creación de un repositorio**

<p>Ahora vamos a crear un repositorio nuevo con el nombre <strong>dpl</strong> , posteriormente mostraremos su contenido, siguiendo los pasos de la imagen…</p>
<img src="https://user-images.githubusercontent.com/73592097/135724319-18f02e19-36e6-4ecb-a5b0-d229befbc32a.png" alt="Creacion de repositorio">

**4. Comprobar el estado del repositorio**

****I. Comprobar el estado del repositorio.****

<p>Si queremos comprobar el estado de nuestro repositorio, utilizaremos este comando, a continuación, veremos un claro ejemplo:</p>
<img src="https://user-images.githubusercontent.com/73592097/135724320-8f730581-32f1-4334-9440-26eb3f24fabf.png" alt="Ver estado de repositorio">

****II. Crear un fichero indice.txt con el siguiente contenido:****

<p>Crearemos un fichero txt, llamado <strong>índice.txt</strong>, que contenga el siguiente texto, una vez terminado, utilizaremos la combinación de teclas <strong>ctrl+d</strong>, para salir.</p>

***<p>\+ Capítulo 1: Instalación de Git por el alumno XXX (donde XXX es el nombre del alumno)</p>***

***<p>\+ Capítulo 2: Flujo de trabajo básico</p>***
<img src="https://user-images.githubusercontent.com/73592097/135724321-b28fb455-88b6-4a39-8de7-6eddc152d7f3.png" alt="Creacion de ficheros">

****III. Comprobar de nuevo el estado del repositorio.****

<p>Veremos los cambios hechos anteriormente…</p>
<img src="https://user-images.githubusercontent.com/73592097/135724323-53c4652f-a73b-4eba-ae74-0e9ce34b440f.png" alt="Cambios anteriormente">

****IV.Añadir el fichero a la zona de intercambio temporal.****

<img src="https://user-images.githubusercontent.com/73592097/135724324-bd08cbb1-005c-490d-83d1-2515845761b2.png" alt="Añadiendo fichero">

****V. Volver a comprobar una vez más el estado del repositorio.****

<p>Volvemos a comprobar si los cambios se han hecho…</p>
<img src="https://user-images.githubusercontent.com/73592097/135724325-1feb55d8-defc-475b-b0a2-77839f79a2bd.png" alt="Comprobar cambios">

**5. Realizando el Commit´s**

<p>Ahora vamos a realizar un commit de los últimos cambios con el mensaje <strong>Añadido índice de la asignatura DPL</strong>, posteriormente podemos ver los cambios en el repositorio con el comando status</p>
<img src="https://user-images.githubusercontent.com/73592097/135724326-b1e666a2-fcd2-4af9-b9df-08120ed6aa46.png" alt="Realizando commit">
<p>Comprobamos el estado del repositorio...</p>
<img src="https://user-images.githubusercontent.com/73592097/135724327-693fe86c-dfeb-431e-a46f-f73273f843ae.png" alt="Estado de repositorio">

**6. Modificación de ficheros**

****I. Cambiar el fichero indice.txt para que contenga lo siguiente:****

<p>En este apartado, vamos a modificar el fichero creado anteriormente (índice.txt), para que contenga el siguiente texto, una vez introducido para salir del editor presionamos la combinación de teclas <strong>CTRL+D</strong>:</p>

***<p>\+ Capítulo 1: Instalación de Git por el alumno XXX (donde XXX es el nombre del alumno)</p>***

***<p>\+ Capítulo 2: Flujo de trabajo básico</p>***

***<p>\+ Capítulo 3: Gestión de ramas</p>***

***<p>\+ Capítulo 4: Repositorios remotos</p>***
<img src="https://user-images.githubusercontent.com/73592097/135724328-a4ac4ffb-8942-4576-9cab-b5bfe7a8fa45.png" alt="Editar fichero">

****II. Mostrar los cambios con respecto a la última versión guardada en el repositorio.****

<p>Para visualizar los cambios, con respecto a la versión anterior, utilizaremos el comando, que se muestra a continuación en la imagen...</p>
<img src="https://user-images.githubusercontent.com/73592097/135724329-6bc7fe4e-78db-4668-90ef-25a764758553.png" alt="Visualizar cambios">

****III. Hacer un commit de los cambios con el mensaje Añadido los capítulos 3 y 4****

<p>Nos encargaremos de añadir los cambios con el nuevo texto a Git...</p>
<img src="https://user-images.githubusercontent.com/73592097/135724330-a3c90526-62d7-4090-813b-7a826a794b7f.png" alt="Añadir cambios">

<p>Posteriormente hacemos un commit de los cambios con el mensaje **Añadido los capítulos 3 y 4...**</p>
<img src="https://user-images.githubusercontent.com/73592097/135724331-17bf0d63-c5c1-4be2-869c-bc9aeab52866.png" alt="Haciendo commits">

**7. Historial de Git**

****I. Mostrar los cambios de la última versión del repositorio con respecto a la anterior.****

<p>Aquí nos encargaremos de mostrar los cambios en la versión que hemos hecho en el repositorio…</p>
<img src="https://user-images.githubusercontent.com/73592097/135724332-c16c1976-599c-4acc-8a2d-cb13b1f28d26.png" alt="Mostrando los cambios">

****II. Cambiar el mensaje del último commit por Añadido el capitulo sobre gestión de ramas al índice.****

<p>Si por alguna razón nos hemos equivocado al subir el commit con otro mensaje que no es el deseado, aquí vamos a mostrar el proceso, en nuestro caso vamos a cambiarlo por el que se describe anteriormente…</p>
<img src="https://user-images.githubusercontent.com/73592097/135724334-8ea988af-33c2-450f-bc3c-ebe3a8b969c9.png" alt="Cambiar commit">

****III. Volver a mostrar los últimos cambios del repositorio.****

<p>Visualizamos los últimos cambios hechos en nuestro repositorio, para comprobar que se han realizado correctamente…</p>
<img src="https://user-images.githubusercontent.com/73592097/135724335-657e1c92-258d-4897-a57d-7205a2b355f2.png" alt="Visualizar ultimos cambios">
<br/>
<hr/>


