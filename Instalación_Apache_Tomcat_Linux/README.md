<img src="https://user-images.githubusercontent.com/73592097/136483158-d4471f26-1bbd-4073-a3aa-4de40e7fb2f8.png" alt="Portada letas">
<img src="https://user-images.githubusercontent.com/73592097/136483060-c3983a06-bbd4-4ed0-9cb7-989a5c13df8f.png" alt="Portada" >
<img src="https://user-images.githubusercontent.com/73592097/136483179-672c1f06-21d8-4777-bed4-755b5237123e.png" alt="Logos">
<br/>
<br/>

# Índice #


## 1. Requisitos previos a la instalación. ##
* ### 1.2 Instalación de Open-JDK en el S.O. ###

## 2. Pasos para realizar la instalación. ##
* ### 2.1 Actualización de los repositorios. ###
* ### 2.2 Instalación de Apache-Tomcat. ###
* ### 2.3 Acceso a Apache-Tomcat. ###
  * #### 2.3.1 Problemas de acceso a Apache-Tomcat. ####

<hr/>
<br/>

**1. Requisitos  previos a la instalación**

<p>Para instalar estos dos servicios web "Apache-Tomcat10", necesitaremos un servidor Ubuntu 20.04 con una cuenta de superusuario no root.</p>
<p>Además tener instalador Java, que en el caso de que no lo tengáis, les mostrare como hacerlo, paso a paso.</p>
<br/>

****1.2 Instalación de Open-JDK en el S.O.****
<p>Primeramente actualizaremos el sistema con este comando..</p>

> sudo apt-get update


<img src="https://user-images.githubusercontent.com/73592097/136546573-372dfb72-ed96-47ce-920c-360cdd4a6dc4.png" alt="actualizacion" width="500px">

<p>Seguidamente instalaremos Java con este comando...</p>

> sudo apt-get install default-jdk


<img src="https://user-images.githubusercontent.com/73592097/136546578-c87c35ab-167f-4a66-8aa1-9fd5cc872962.png" alt="Instalacion" width="500px">

<p>Posteriormente, comprobaremos que se ha instalado en nuestro sistema, el comando es...</p>

> java --version


<img src="https://user-images.githubusercontent.com/73592097/136546582-c4a149e3-aef6-4927-baa7-e095b29f86f1.png" alt="Comprobacion de java" width="500px">

**2. Pasos para realizar la instalación**

  ***2.1 Actualización de los repositorios***

<p>Actualizaremos tanto el repositorio como el S.O. para asegurarnos que va hacer una instalación segura y actualizada, el comando seria...</p>

>   sudo apt update && sudo apt upgrade


<img src="https://user-images.githubusercontent.com/73592097/136546585-177f3a5e-dded-41ed-903c-97737b2878cb.png" alt="Actualizacion de repositorios" width="500px">

  ***2.2 Instalación de Apache-Tomcat***

<p>Procederemos a descargar Tomcat 20 para Ubuntu 20.04 desde la terminal con el siguiente comando...</p>

>   wget https://downloads.apache.org/tomcat/tomcat-10/v10.0.12/bin/apache-tomcat-10.0.12.tar.gz


<img src="https://user-images.githubusercontent.com/73592097/136546587-c244897d-446e-42e1-8332-6429b8385549.png" alt="Descarga de tomcat" width="500px">
<p> Creamos el nuevo usuario y grupo Tomcat 10 para configurar el servicio en el sistema. El comando es...</p>

>sudo useradd -U -m -d /opt/tomcat -k /dev/null -s /bin/false tomcat


<img src="https://user-images.githubusercontent.com/73592097/136546588-5e1ffa72-9c9d-401c-86f0-5d4502817bed.png" alt="Creacion de usuario" width="500px">
<p> Luego descomprimimos el paquete directamente en su ubicación </p>

>   sudo tar xf apache-tomcat-10.0.12.tar.gz -C /opt/tomcat/


<img src="https://user-images.githubusercontent.com/73592097/136546589-a411a58a-2d6f-484c-800c-bfd0da509779.png" alt="Descomprimir ficheros" width="500px">
<p> Asignamos como propietario los archivos Tomcat10 al usuario que hemos creado anteriormente con este comando...</p>

>   sudo chown -R tomcat: /opt/tomcat/


<img src="https://user-images.githubusercontent.com/73592097/136546590-899e5699-6cb3-43be-acdb-60fa3b904cd4.png" alt="Assignacion como propietario" width="500px">
<p>Renombramos el directorio de instalación, creando un enlace simbólico para facilitar la instalación y configuración, el comando seria...</p>

>  sudo ln -s /opt/tomcat/apache-tomcat-10.0.12/ /opt/tomcat/apache-tomcat


<img src="https://user-images.githubusercontent.com/73592097/136546591-5d6be2a3-426d-46ad-a86a-c4890c5033cd.png" alt="renombrar directorio" width="500px">
<p>Vamos a configurar e iniciar el servicio, creando un archivo en la unidad para systemd, el comando seria.... </p>

> sudo nano /etc/systemd/system/tomcat10.service


<img src="https://user-images.githubusercontent.com/73592097/136546595-b2834684-1e32-4ae9-a56d-49f434ce1f3b.png" alt="Configurar e iniciar el servicio" width="500px">

<p>Y el contenido que debemos copiar es el siguiente.....</p>

<img src="https://user-images.githubusercontent.com/73592097/136546597-b4cf325a-8e9d-46c1-a320-d8476ca6de38.png" alt="Contenido a copiar" width="500px">

<p>Iniciamos el servicio, con el siguiente comando....</p>

>  sudo systemctl start tomcat10


<img src="https://user-images.githubusercontent.com/73592097/136546592-48dda9f5-e186-45ce-baa4-a6ee77ce88d9.png" alt="iniciando servicio" width="500px">

<p>Una vez iniciado el servicio, verificamos el estado del mismo, el comando seria el siguiente...</p>

>systemctl status tomcat10


<img src="https://user-images.githubusercontent.com/73592097/136546593-0d85fcf1-2b6e-475a-a6da-ab31f380b116.png" alt="verificar el servicio" width="500px">

<p>Ahora habilitamos el siguiente servicio, para que Tomcat 10, inicie automáticamente en cada arranque de Ubuntu, con el siguiente comando...</p>

>sudo systemctl enable tomcat10


<img src="https://user-images.githubusercontent.com/73592097/136546594-14181620-c4f8-4730-b3e5-bde5a6cbba9f.png" alt="habilitar servicio" width="500px">

  ***2.3 Acceso a Apache-Tomcat***

  <p>Accederemos a Tomcat10 desde un navegador, indicándole la dirección del servidor y su puerto de conexión, que hemos configurado</p>

  <p>Si tenemos problemas de acceso, mira el siguiente apartado</p>

  ****2.3.1 Problema de acceso a Apache-Tomcat****

<p>Ahora vamos a realizar el cambio de puerto de la aplicación, que se encuentra en el archivo server.xml, el comando seria el siguiente</p>

<img src="https://user-images.githubusercontent.com/73592097/136551630-ff80a425-5137-4af9-a0e2-cb181d13c525.png" alt="realizar cambio" width="500px">

<p>Nos encontramos con esta configuración, con el puerto 8080</p>

<img src="https://user-images.githubusercontent.com/73592097/136551793-34e75b43-37eb-4d41-86a9-7633eb6449c7.png" alt="configuracion predeterminada" width="500px">

<p>Ahora vamos a cambiar el puerto 8080, por 8083</p>

<img src="https://user-images.githubusercontent.com/73592097/136551872-810083fe-4d44-487c-ad67-3a62226fa87a.png" alt="cambio de puerto" width="500px">

<p>Una vez cambiado el puerto guardamos el fichero CTRL+O, y salimos de la aplicación CTRL+ X</p>

<p>Accederemos nuevamente al navegador web y en la url ponemos la dirección del servidor y el puerto, finalmente nos tendría que salir una ventana similar a esta</p>

<img src="https://user-images.githubusercontent.com/73592097/136551938-c432ad8e-63ec-47c1-93dc-dbc42bdbb5d7.png" alt="tomcar en el navegador" width="500px">

<p>Enhorabuena ya tenemos la instalación Apache-Tomcat10</p>
