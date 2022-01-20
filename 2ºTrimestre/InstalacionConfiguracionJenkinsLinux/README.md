<img alt="README-1eac2bfe.png" src="assets/README-1eac2bfe.png" width="" height="" >
<hr/>

# Índice #

## 1. Requisitos básicos ##

## 2. Creación del dominio ##

## 3. Instalación de  Jenkins en Docker ##

## 4. Instalación de Jenkins a través de Docker y Docker-Compose ##

- ### 4.1 Dockerfile ###
- ### 4.2 Plugins.txt ###
- ### 4.3 Docker-Compose###
- ### 4.4 Construcción de la imagen###


<hr/>

**1. Requisitos básicos**

- <p>Tener docker instalado</p>
- <p>Tener docker-compose instalado</p>

**2. Creación del dominio**
<p>Nos situamos en la carpeta de apache sites-available</p>

<img alt="README-96d09888.png" src="assets/README-96d09888.png" width="800px"/>

<p>Copiamos la carpeta de la practica anterior *joelic.conf* y en su lugar creamos jekins.joel.conf</p>

<img alt="README-f0b244db.png" src="assets/README-f0b244db.png" width="800px"/>

<p>Configuramos la carpeta nueva</p>

<img alt="README-750c374c.png" src="assets/README-750c374c.png" width="800px"/>

<p>Habilitamos el sitio</p>
<img alt="README-97dd9aa7.png" src="assets/README-97dd9aa7.png" width="800px"/>

<p>Reiniciamos apache</p>

<img alt="README-995ac3cb.png" src="assets/README-995ac3cb.png" width="800px"/>

<p>Añadimos el dominio en /etc/hosts</p>

<img alt="README-6e9dc1af.png" src="assets/README-6e9dc1af.png" width="800px"/>


**3. Instalación de Jenkins en Docker**

<Antes de esto eliminamos todos contenedores,imagenes y volumnes en docker>

<p>Nos dirigimos a <a href="">https://hub.docker.com/</a> y buscamos la imagen oficial de jenkins </p>

<p>Descargamos la imagen de jenkins para docker con el siguiente comando...</p>

>  docker pull jenkins/jenkins:lts

<img alt="README-7c50b95d.png" src="assets/README-7c50b95d.png" width="800px"/>

<p>Verificamos que la imagen se ha descargado corrrectamente con el siguiente comando...</p>

>  docker images

<img alt="README-842c1dbd.png" src="assets/README-842c1dbd.png" width="800px"/>

<p>Ahora ejecutamos jenkins como contenedor Docker exponiendolo en el puerto 8080 del ordenador local. Verificamos nuestro /your/home:/ con el comando </p>

> docker run -p 8080:8080 -p 50000:50000 -v /your/home:/var/jenkins_home jenkins/jenkins:lts

<img alt="README-ebff2a3b.png" src="assets/README-ebff2a3b.png" width="800px"/>

<p>Si nos muestra el mensaje de error anterior hacemos lo siguiente</p>

<p>Listamos los puertos activos y vemos quien los esta ocupando con el siguiente comando de la imagen y luego eliminamos el servicio de ese puerto </p>

<img alt="README-817c5d16.png" src="assets/README-817c5d16.png" width="800px"/>

<p>Volvemos a lanzar el comando anterior</p>

<img alt="README-0194b227.png" src="assets/README-0194b227.png" width="800px"/>

<p>Se genera una contraseña que debemos copiar</p>

<img alt="README-eefd7947.png" src="assets/README-eefd7947.png" width="800px"/>

<p>Verifica que puedas ingresar al contenedor a través del navegador web de tu preferencia.
</p>

<img alt="README-a7440615.png" src="assets/README-a7440615.png" width="800px"/>
<p>Lo config</p>

**4. Requisitos básicos**

<p>Creamos una carpeta que va a tener los ficheros de configuración de jenkins</p>

<img alt="README-6f95665f.png" src="assets/README-6f95665f.png" width=""/>
<hr/>

***4.1 Dockerfile***
<p>Posteriormente nos creamos un fichero dockerfile con el contenido siguiente</p>

<img alt="README-501f14a0.png" src="assets/README-501f14a0.png" width="800px"/>

<p>Explicación del fichero dockerfile</p>

<img alt="README-b951611c.png" src="assets/README-b951611c.png" width="800px"/>
<hr/>

***4.2 Plugins.txt***

<p>Ahora creamos un fichero llamado plugins.txt que contienen los plugins a instalar en jekins, el contenido sera el siguiente</p>

<img alt="README-21560349.png" src="assets/README-21560349.png" width="800px"/>
<hr/>

***4.3 Docker-Compose.yml***

<p>Nos queda por crear nuestro docker-compose.yml con el contenido siguiente</p>

<img alt="README-95988536.png" src="assets/README-95988536.png" width="800px"/>

<p>Explicación del fichero docker-compose.yml</p>

<img alt="README-042701c7.png" src="assets/README-042701c7.png" width="800px"/>

<p>Creamos una carpeta llamada jenkins y metemos los ficheros dockerfile y pulgins.txt dentro de ella</p>

<p>Teniendo una estructura similar a la siguiente</p>
<img alt="README-6f95665f.png" src="assets/README-6f95665f.png" width=""/>
<hr/>

***4.4 Construcción de la imagen***

<p>Para construir la imagen ejecutamos el siguiente comando:</p>

> docker-compose build

<img alt="README-5b4753e0.png" src="assets/README-5b4753e0.png" width="800px"/>

<p>Para arrancar el contenedor con Jenkins ejecutamos el siguiente comando:</p>

> docker-compose up -d

<img alt="README-1d92eea6.png" src="assets/README-1d92eea6.png" width="800px"/>

<p>Arrancado jenkins accedemos a nuestro dominio para entrar en la consola jenkins</p>

<p>Para obtener la contraseña del usuario admin de Jenkins ejecutamos el siguiente comando:</p>

> docker exec -it dockerjenkins_master_1 cat /var/jenkins_home/secrets/initialAdminPassword

<img alt="README-f1123d8f.png" src="assets/README-f1123d8f.png" width="800px"/>

<p>Ahora podemos configurar jenkins en docker</p>

<img alt="README-ab121647.png" src="assets/README-ab121647.png" width="800px"/>

<hr/>

Enlace github: <a href="https://github.com/joel92MM/Git/tree/main/2ºTrimestre/InstalacionConfiguracionJenkinsLinuxDocker">enlace</a>
