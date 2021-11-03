


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




![2](https://user-images.githubusercontent.com/73592097/139929327-09744aa7-3850-47ac-8b8e-e565b23f7ee6.png)
![3](https://user-images.githubusercontent.com/73592097/139929330-a05a29a6-2685-454b-a2eb-afe38f1d615c.png)
![4](https://user-images.githubusercontent.com/73592097/139929335-4c7cfa5d-3425-4372-a409-fbfcd9fe19c3.png)
![5](https://user-images.githubusercontent.com/73592097/139929338-482ef84d-637a-4c35-aa24-6ef1b15d0f4d.png)
![1](https://user-images.githubusercontent.com/73592097/139929430-eda714be-ed1e-4649-83e5-631d37ea7a57.png)


![6](https://user-images.githubusercontent.com/73592097/139934580-21963bbc-6e50-490f-a93d-4f451f16f662.png)
![7](https://user-images.githubusercontent.com/73592097/139934602-07f5fd9e-027b-4653-a60e-8017956443eb.png)
![8](https://user-images.githubusercontent.com/73592097/139934609-044f6d8a-852c-498c-9ffb-51f7e21250a6.png)
![9](https://user-images.githubusercontent.com/73592097/139934619-a8e28755-bca8-4ca2-b38b-2ff1211e6f42.png)
![10](https://user-images.githubusercontent.com/73592097/139934624-d799a594-17bd-4801-b9be-91e8b1187a39.png)


![11](https://user-images.githubusercontent.com/73592097/140099368-04b5d0f4-66fa-4309-8771-ed354bd1a5ba.png)
![12](https://user-images.githubusercontent.com/73592097/140099381-29b54087-104a-4681-a3c9-fed55a0e9614.png)
![13](https://user-images.githubusercontent.com/73592097/140099393-97bed366-166c-47a3-80a5-b91d86303dd2.png)
