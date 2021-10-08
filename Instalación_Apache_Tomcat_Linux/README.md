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

<img src="" alt="actualizacion" width="500px">

<p>Seguidamente instalaremos Java con este comando...</p>

> sudo apt-get install default-jdk

<p>Posteriormente, comprobaremos que se ha instalado en nuestro sistema, el comando es...</p>

> java --version

**2. Pasos para realizar la instalación**

  ***2.1 Actualización de los repositorios***

<p>Actualizaremos tanto el repositorio como el S.O. para asegurarnos que va hacer una instalación segura y actualizada, el comando seria...</p>

>   sudo apt update && sudo apt upgrade

  ***2.2 Instalación de Apache-Tomcat***

<p>Procederemos a descargar Tomcat 20 para Ubuntu 20.04 desde la terminal con el siguiente comando...</p>

>   wget https://downloads.apache.org/tomcat/tomcat-10/v10.0.12/bin/apache-tomcat-10.0.12.tar.gz

<p> Creamos el nuevo usuario y grupo Tomcat 10 para configurar el servicio en el sistema. El comando es...</p>

>sudo useradd -U -m -d /opt/tomcat -k /dev/null -s /bin/false tomcat

<p> Luego descomprimimos el paquete directamente en su ubicación </p>

>   sudo tar xf apache-tomcat-10.0.12.tar.gz -C /opt/tomcat/

<p> Asignamos como propietario los archivos Tomcat10 al usuario que hemos creado anteriormente con este comando...</p>

>   sudo chown -R tomcat: /opt/tomcat/

<p>Renombramos el directorio de instalación, creando un enlace simbólico para facilitar la instalación y configuración, el comando seria...</p>

>  sudo ln -s /opt/tomcat/apache-tomcat-10.0.12/ /opt/tomcat/apache-tomcat

<p>Vamos a configurar e iniciar el servicio, creando un archivo en la unidad para systemd, el comando seria.... </p>

> sudo nano /etc/systemd/system/tomcat10.service


<p>Y el contenido que debemos copiar es el siguiente.....</p>

<p>Iniciamos el servicio, con el siguiente comando....</p>

>  sudo systemctl start tomcat10

<p>Una vez iniciado el servicio, verificamos el estado del mismo, el comando seria el siguiente...</p>

>systemctl status tomcat10

<p>Ahora habilitamos el siguiente servicio, para que Tomcat 10, inicie automáticamente en cada arranque de Ubuntu, con el siguiente comando...</p>

>sudo systemctl enable tomcat10

  ***2.3 Acceso a Apache-Tomcat***

  <p>Accederemos a Tomcat10 desde un navegador, indicándole la dirección del servidor y su puerto de conexión, que hemos configurado</p>

  <p>Si tenemos problemas de acceso, mira el siguiente apartado</p>

  ****2.3.1 Problema de acceso a Apache-Tomcat****



<p>Ahora vamos a realizar el cambio de puerto de la aplicación, que se encuentra en el archivo server.xml, el comando seria el siguiente</p>
<p>Nos encontramos con esta configuración, con el puerto 8080</p>
<p>Ahora vamos a cambiar el puerto 8080, por 8083</p>
<p>Una vez cambiado el puerto guardamos el fichero CTRL+O, y salimos de la aplicación CTRL+ X</p>
<p>Accederemos nuevamente al navegador web y en la url ponemos la dirección del servidor y el puerto, finalmente nos tendría que salir una ventana similar a esta</p>
<p>Enhorabuena ya tenemos la instalación Apache-Tomcat10</p>
