


# Índice #

## 1. Instalar Docker. ##

## 2. Trabajar con imágenes de Docker ##

## 3. Administrar contenedores de Docker ##

<hr/>
<br/>

<p>Actualizaremos la lista de paquetes con el siguiente comando..</p>

>sudo apt update

<p>Instalarmos algunos paquetes de requisitos previos que permitan a apt usar paquetes a través
de HTTPS</p>

> sudo apt install apt-transport-https ca-certificates curl software-properties-common

<p>Luego, añade la clave de GPG para el repositorio oficial de Docker en su sistema:</p>

> curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo apt-key add -

<p>Agrega el repositorio de Docker a las fuentes de APT:</p>

> sudo add-apt-repository "deb [arch=amd64] https://download.docker.com/linux/ubuntu focal stable"

<p>A continuación, actualice el paquete de base de datos con los paquetes de Docker del repositorio recién agregado:</p>

> sudo apt update

<p>Asegúrate de estar a punto de realizar la instalación desde el repositorio de Docker en lugar del repositorio predeterminado de Ubuntu:</p>

> apt-cache policy docker-ce

<p>Instalamos Docker</p>

> sudo apt install docker-ce

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
