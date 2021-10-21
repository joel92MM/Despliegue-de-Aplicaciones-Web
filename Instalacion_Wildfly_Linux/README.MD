**Editando**

<img src="https://user-images.githubusercontent.com/73592097/137605961-10eb3c30-0b53-494a-96ad-23616bf2fed2.png" alt="Portada">


<br/>
<hr/>

# Índice #

## 1. Requisitos previos para la instalación ##

*  ## 1.1 Instalación de Java y Maven ##


## 2. Pasos para realizar la instalación en local ##

*  ## 2.1 Actualización de los repositorios ##

*  ## 2.2 Instalación de WildFly ##

*  ## 2.3 Configurar a WildFly ##

*  ## 2.4 Acceso a WildFly ##

## 3. Como añadir usuarios a WildFly ##

*  ## 3.1 Gestionar la consola de forma remota ##

<hr/>

**1. Requisitos  previos a la instalación**

<p>Tener un S.O. Ubuntu 20.04 con un cuenta de superusuario no root. También es necesario disponer de Java instalado y Maven.</p>

***1.1 Instalación de Java y Maven***
<p>Prioritariamente tenemos que tener instalado Java y Maven en nuestro equipo, para asegurarnos ejecutaremos los siguientes comandos que les muestro a continuación: </p>

> java --version

<img src="https://user-images.githubusercontent.com/73592097/138179714-6e2d3432-a607-44c4-a811-993b02f6de96.png" alt="versión de maven" width="800px">

<br/>

> mvn -version

<img src="https://user-images.githubusercontent.com/73592097/138179719-3f36224c-9360-43c9-b20d-fa0ba55dcc90.png" alt="versión de java" width="800px">


**2. Pasos para realizar la instalación en local**

***2.1 Instalación de Java y Maven***


<p>Actualizaremos los repositorios y el sistema operativo para comprobar que la instalación de wildfly, en una instalación de Ubuntu segura y actualizada</p>

<p>Mediante este comando </p>

>  sudo apt update && sudo apt upgrade

<img src="https://user-images.githubusercontent.com/73592097/138179721-b00c6d26-fff0-4dd8-b68f-bcdf5b523385.png" alt="actualización de repositorios" width="800px">

***2.2 Instalación de WildFly***

<p>A continuación procederemos a descargar WildFly, para Ubuntu 20.04 LTS desde la página del sitio oficial, donde estará disponible una versión estable, veremos un paquete en varios formatos ZIP, donde vamos a descargarlo con el siguiente comando..</p>

<p>Para ello nos situamos en la carpeta /tmp para descargarlo </p>

<img src="https://user-images.githubusercontent.com/73592097/138187286-b6a68684-bd2f-4d0c-a280-022e81eda292.png" alt="carpeta tmp" width="800px">

>  wget https://github.com/wildfly/wildfly/releases/download/25.0.0.Final/wildfly-25.0.0.Final.tar.gz


<img src="https://user-images.githubusercontent.com/73592097/138187278-46d22053-12b8-413e-95d2-c4ed712750a8.png" alt="descarga del paquete" width="800px">

<p>Ahora crearemos el nuevo grupo y usuario de wildfly, con el siguiente comando...</p>

> sudo groupadd -r wildfly
sudo useradd -r -g wildfly -d /opt/wildfly -s /sbin/nologin wildfly


<img src="https://user-images.githubusercontent.com/73592097/138187274-1195eee4-ca32-45f2-9e5a-4d4f0f36f2d7.png" alt="creación del nuevo grupo y usuario" width="800px">

<p>Descomprimiremos el paquete  descargado directamente desde su ubicación, con el siguiente comando</p>

> sudo tar xvf /tmp/wildfly-25.0.0.Final.tar.gz -C /opt/

<img src="https://user-images.githubusercontent.com/73592097/138191580-3ce84017-ec3c-4ca7-bac6-a46abce4bae0.png" alt="descomprimir el paquete" width="800px">



<p>Crearemos un enlace simbólico, con el siguiente comando...</p>

> sudo ln -s /opt/wildfly-25.0.0.Final.zip /opt/wildfly


<img src="https://user-images.githubusercontent.com/73592097/138191807-1d35c458-f003-4f1d-84b6-8e20354c41d9.png" alt="simbolico" width="800px">

<p>Daremos acceso al usuario y grupo wildfly</p>

> sudo chown -RH wildfly: /opt/wildfly

<img src="https://user-images.githubusercontent.com/73592097/138192154-2be98804-925d-4add-81ce-9056030977e7.png" alt="acceso a usuario y grupo" width="800px">



<p>Creamos la carpeta de servicio de Wildfly en el directorio /etc/</p>

> sudo mkdir -p /etc/wildfly

<img src="https://user-images.githubusercontent.com/73592097/138192915-29f93f42-14fe-44a2-b41d-4da8d7f613cc.png" alt="crear directorio" width="800px">

<p>Luego configuramos e iniciamos el servicio, con el siguiente comando...</p>

> sudo cp /opt/wildfly/docs/contrib/scripts/systemd/wildfly.conf /etc/wildfly/

> sudo nano /etc/wildfly/wildfly.conf

> **WILDFLY_BIND=0.0.0.0**

> sudo cp /opt/wildfly/docs/contrib/scripts/systemd/launch.sh /opt/wildfly/bin/

> sudo sh -c 'chmod +x /opt/wildfly/bin/*.sh'

> sudo cp /opt/wildfly/docs/contrib/scripts/systemd/wildfly.service /etc/systemd/system/

> sudo systemctl daemon-reload

<img src="https://user-images.githubusercontent.com/73592097/138192997-ffedbe15-dc2d-4e4a-a9a8-0187bc13c1d1.png" alt="configurar e iniciar el servicio" width="800px">


<img src="https://user-images.githubusercontent.com/73592097/138193053-868c9d18-9d44-41c3-bc26-603e3d71ba6d.png" alt="configurar e iniciar el servicio2" width="800px">

<img src="https://user-images.githubusercontent.com/73592097/138193243-3e44ca64-546f-4b1e-9d60-dbd2fc1d42ac.png" alt="configurar e iniciar el servicio3" width="800px">

<img src="https://user-images.githubusercontent.com/73592097/138193533-96322ee1-88f1-4870-bedd-1b2f13fb76c2.png" alt="configurar e iniciar el servicio4" width="800px">

<img src="https://user-images.githubusercontent.com/73592097/138193561-15392a97-9e12-490c-9a62-78d7426aa5ab.png" alt="configurar e iniciar el servicio5" width="800px">

<p>Iniciamos el servicio con el siguiente comando....</p>

>   sudo systemctl start wildfly

<img src="https://user-images.githubusercontent.com/73592097/138195556-bbd636d7-6e8c-47ef-a12b-6121e8a7abda.png" alt="iniciar el servicio" width="800px">

<p>Verificaremos el estado del servicio con el comando...</p>

> sudo systemctl status wildfly

<img src="https://user-images.githubusercontent.com/73592097/138195557-717f1f0d-69e5-423a-be24-9b0578aae6ff.png" alt="verificacion del servicio" width="800px">

<p>Para que wildfly inicie el servicio automáticamente en cada arranque, debemos habilitar el servicio con el comando...</p>

> sudo systemctl enable wildfly

<img src="https://user-images.githubusercontent.com/73592097/138195562-13a1177f-0a9a-4967-b6ea-fdc7dad865ea.png" alt="inicio automatico del servicio" width="800px">

***2.3 Configurar a WildFly***

<p>Seguidamente vamos a permitir el tráfico por un puerto especifico, en nuestro caso utilizaremos el 8084, con el siguiente comando..</p>

> sudo ufw allow 8084/tcp

<img src="https://user-images.githubusercontent.com/73592097/138195563-d554c43e-2aa3-48db-8bdc-b80b15100153.png" alt="permitir tráfico" width="800px">

***2.4 Acceso a WildFly***

<p>Accederemos a WildFly desde un navegador, indicándole (IP, nombre DNS, dominio, etc.) y el puerto de conexión, el 8084. Y tendremos desplegado Wildfly.</p>

<img src="" alt="acceso por navegador" width="800px">

**3. Como añadir usuarios a WildFly**

<p>Crearemos el usuario administrador, con el siguiente comando</p>

> sudo /opt/wildfly/bin/add-user.sh

<img src="" alt="creacion usuario administrador" width="800px">

<p>Seleccionaremos la opción a, indicándole que es un usuario de gestión</p>

<img src="" alt="seleccion de opcion" width="800px">

<p>Obtenemos un mensaje como el siguiente</p>

> $ ./add-user.sh

> What type of user do you wish to add?
 a) Management User (mgmt-users.properties)
 b) Application User (application-users.properties)
(a): a

> Enter the details of the new user to add.
Using realm 'ManagementRealm' as discovered from the existing property files.
Username : admin123
<br/>

> Password recommendations are listed below. To modify these restrictions edit the add-user.properties configuration file.

<br/>
 >  The password should be different from the username

 <br/>


 > The password should not be one of the following restricted values {root, admin, administrator}

 <br/>

> The password should contain at least 8 characters, 1 alphabetic character(s), 1 digit(s), 1 non-alphanumeric symbol(s)

 <br/>

> Password :

<br/>

> Re-enter Password :

<br/>

> What groups do you want this user to belong to? (Please enter a comma separated list, or leave blank for none)[  ]:
About to add user 'admin123' for realm 'ManagementRealm'
Is this correct yes/no? yes
Added user 'admin123' to file
 value="UGFzc3dvcmQxMjM="
 ... />


<img src="" alt="obtencion de mensaje" width="800px">

***3.1 Gestionar la consola de forma remota***

<p>Ejecutaremos el siguiente comando para realizar la configuración, con el siguiente comando..</p>

>   sudo nano /etc/wildfly/wildfly.conf

>  WILDFLY_CONSOLE_BIND=0.0.0.0

>  sudo nano /opt/wildfly/bin/launch.sh


<img src="" alt="realizando configuración" width="800px">

<p>Nos saldrá unas opciones que indican en que modo desearemos lanzar el servidor, (standalone o domain)</p>

<img src="" alt="obtencion de mensaje" width="800px">

<p>Para finalizar, ejecutamos el siguiente comando...</p>

>  sudo systemctl restart wildfly

>  sudo nano /etc/systemd/system/wildfly.service

>  ExecStart=/opt/wildfly/bin/launch.sh $WILDFLY_MODE $WILDFLY_CONFIG $WILDFLY_BIND $WILDFLY_CONSOLE_BIND

>  sudo systemctl daemon-reload

>  sudo systemctl restart wildfly

<img src="" alt="finalización" width="800px">

<p>Abriremos la consola de cli, con el siguiente comando...</p>

>   cd /opt/wildfly/bin/
  ./jboss-cli.sh --connect

  <img src="" alt="consola cli" width="800px">
