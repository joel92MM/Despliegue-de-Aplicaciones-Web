
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

***2.1 Instalando el paquete vsftpd***

<p>Vamos a instalar el paquete ftp con el comando siguiente..</p>

> sudo apt install -y vsftpd

<p>Obtenemos un mensaje similar al siguiente</p>

<p>Para comprobar el estado del servidor FTP utilizamos el comando..</p>

> sudo systemctl status vsftpd

<p>Si el firewall UFW está activado en Ubuntu debemos de permitir el acceso a los puertos estándar del servicio FTP, con el comando...</p>

> sudo ufw allow ftp

<p>Y el puerto de datos, para el modo activo con el comando...</p>

> sudo ufw allow ftp-data

**3. Verificar el servicio FTP en Ubuntu**
<p></p>
<p></p>
<p></p>
<p></p>
<p></p>
<p></p>
<p></p>
<p></p>
<p></p>
