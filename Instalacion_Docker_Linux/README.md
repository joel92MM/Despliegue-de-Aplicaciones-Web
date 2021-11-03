


# Índice #

## 1. Instalar Docker. ##

## 2. Trabajar con imágenes de Docker ##

## 3. Administrar contenedores de Docker ##

<hr/>
<br/>


<p>Actualizaremos la lista de paquetes con el siguiente comando..</p>

>sudo apt update

![1](https://user-images.githubusercontent.com/73592097/139929430-eda714be-ed1e-4649-83e5-631d37ea7a57.png)

<p>Instalarmos algunos paquetes de requisitos previos que permitan a apt usar paquetes a través
de HTTPS</p>

> sudo apt install apt-transport-https ca-certificates curl software-properties-common

![2](https://user-images.githubusercontent.com/73592097/139929327-09744aa7-3850-47ac-8b8e-e565b23f7ee6.png)

<p>Luego, añade la clave de GPG para el repositorio oficial de Docker en su sistema:</p>

> curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo apt-key add -

![3](https://user-images.githubusercontent.com/73592097/139929330-a05a29a6-2685-454b-a2eb-afe38f1d615c.png)

<p>Agrega el repositorio de Docker a las fuentes de APT:</p>

> sudo add-apt-repository "deb [arch=amd64] https://download.docker.com/linux/ubuntu focal stable"

![4](https://user-images.githubusercontent.com/73592097/139929335-4c7cfa5d-3425-4372-a409-fbfcd9fe19c3.png)

<p>A continuación, actualice el paquete de base de datos con los paquetes de Docker del repositorio recién agregado:</p>

> sudo apt update

![5](https://user-images.githubusercontent.com/73592097/139929338-482ef84d-637a-4c35-aa24-6ef1b15d0f4d.png)


<p>Asegúrate de estar a punto de realizar la instalación desde el repositorio de Docker en lugar del repositorio predeterminado de Ubuntu:</p>

> apt-cache policy docker-ce

![6](https://user-images.githubusercontent.com/73592097/139934580-21963bbc-6e50-490f-a93d-4f451f16f662.png)


<p>Instalamos Docker</p>

> sudo apt install docker-ce

![7](https://user-images.githubusercontent.com/73592097/139934602-07f5fd9e-027b-4653-a60e-8017956443eb.png)

<p>Con esto, Docker quedará instalado, el demonio se iniciará y el proceso se habilitará para ejecutarse en el inicio. Compruebe que funcione:</p>

> sudo systemctl status docker

<p>El resultado es el siguiente</p>

<p>docker.service - Docker Application Container Engine
     Loaded: loaded (/lib/systemd/system/docker.service; enabled; vendor preset>
     Active: active (running) since Fri 2021-10-29 19:21:13 WEST; 28min ago
TriggeredBy: ● docker.socket
       Docs: https://docs.docker.com
   Main PID: 3169 (dockerd)
      Tasks: 10
     Memory: 38.3M
     CGroup: /system.slice/docker.service
             └─3169 /usr/bin/dockerd -H fd:// --containerd=/run/containerd/cont>
</p>

![8](https://user-images.githubusercontent.com/73592097/139934609-044f6d8a-852c-498c-9ffb-51f7e21250a6.png)

<p>Asignaremos permisos para poder acceder a las imágenes, mediante este comando</p>

![9](https://user-images.githubusercontent.com/73592097/139934619-a8e28755-bca8-4ca2-b38b-2ff1211e6f42.png)

<p>Para verificar si puede acceder a imágenes, insertamos el siguiente comando</p>

![10](https://user-images.githubusercontent.com/73592097/139934624-d799a594-17bd-4801-b9be-91e8b1187a39.png)

<p>Con el siguiente comando veremos los contenedores activos de Docker, utilizaremos el comando...</p>

>  sudo docker ps

<p>Para ver todos los contenedores, activos e inactivos, ejecute docker ps con el conmutador -a:</p>

>  docker ps -a

<p>Para ver el último contenedor que creó, utilizaremos el comando../p>

>   docker ps -l

<p>Listar las imágenes de Docker de nuevo, con el siguiente comando..</p>

>sudo docker images


<hr/>

Enlace github: <a href="https://github.com/joel92MM/Git/tree/main/Instalacion_Docker_Linux">enlace</a>
