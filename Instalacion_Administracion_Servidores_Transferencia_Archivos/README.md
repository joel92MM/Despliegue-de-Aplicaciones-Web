
![](assets/README-6b317474.GIF)
# Índice #

## 1. Requisitos básicos ##

## 2. ¿Cómo instalar FTP? ##

*  ## 2.1 Instalando el paquete vsftpd  ##

## 3. Verificar el servicio FTP en Ubuntu  ##

## 4. Configurar el servidor FTP ##

## 5. Instalación de un cliente o utilización de un cliente ##


<hr/>

**1. Requisitos básicos**

- Disponer de una máquina Ubuntu 20.04
- Internet

**2. ¿Cómo instalar FTP?**
<p>Vamos a instalar el servidor FTP vsFTPd en Ubuntu 20.04 desde los repositorios de la distribución, así que la primera acción será actualizar la información de los repositorios, con el comando...</p>

> sudo apt update && apt upgrade

![Captura de pantalla de 2021-12-19 13-47-29](https://user-images.githubusercontent.com/73592097/146677164-4dfcea80-71bd-4bbc-96e5-1921a035916e.png)

***2.1 Instalando el paquete vsftpd***

<p>Vamos a instalar el paquete ftp con el comando siguiente..</p>

> sudo apt install -y vsftpd

<p>Obtenemos un mensaje similar al siguiente</p>

![1](https://user-images.githubusercontent.com/73592097/146677091-8b6a5cb7-bdae-4214-9b05-93bc209f9d41.png)

<p>Para comprobar el estado del servidor FTP utilizamos el comando..</p>

> sudo systemctl status vsftpd

![2](https://user-images.githubusercontent.com/73592097/146677092-5e238c07-1ff1-499c-9b3c-af81dc0147dd.png)

<p>Si el firewall UFW está activado en Ubuntu debemos de permitir el acceso a los puertos estándar del servicio FTP, con el comando...</p>

> sudo ufw allow ftp

![3](https://user-images.githubusercontent.com/73592097/146677093-0cb13dfe-9102-4af2-a4a9-c1fa9b011cfb.png)

<p>Y el puerto de datos, para el modo activo con el comando...</p>

> sudo ufw allow ftp-data

![4](https://user-images.githubusercontent.com/73592097/146677094-476eacb8-db0b-4916-9cdc-a2dcad6008fd.png)

<p>Creamos una copia de el archivo de configuracion original de ftp, con el comando</p>

![5](https://user-images.githubusercontent.com/73592097/146677095-4df6a1f6-fa63-4453-a72f-1024b34715f9.png)

**3. Verificar el servicio FTP en Ubuntu**
<p>Accederemos al navegadorn donde introducimos la direccion ftp://ip, pero muestra solo la ventana siguiente</p>

![Captura de pantalla de 2021-12-19 14-58-41](https://user-images.githubusercontent.com/73592097/146679983-6e5f5236-cd56-44ee-8631-20c0869d3682.png)

<p>De otra manera, si accedemos por el terminal introduciendo ftp ip, entramos dentro pidiendo las credenciales de nuestro usuario con contraseña para entrar</p>

![Captura de pantalla de 2021-12-19 15-03-15](https://user-images.githubusercontent.com/73592097/146679984-1d84e498-2ce4-4adb-a2f5-9d683f98890c.png)

<p></p>
<p></p>
<p></p>
<p></p>
<p></p>
<p></p>
<p></p>
