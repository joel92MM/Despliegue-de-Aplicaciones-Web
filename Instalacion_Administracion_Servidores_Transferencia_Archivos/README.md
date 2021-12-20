
<img alt="README-0d42f59c.png" src="assets/README-0d42f59c.png" width="" height="" >
<hr/>

# Índice #

## 1. Requisitos básicos ##

## 2. Busquedas de imágenes creadas ##

## 3. Trabajar con la imagen atmoz  ##

## 4. Verificar la imagen ##

## 5. Configurar el directorio home en la máquina host. ##

## 6. SFTP Multiusuario ##

<hr/>

**1. Requisitos básicos**

- Disponer de una máquina Ubuntu 20.04
- Internet

**2. Búsquedas de imágenes creadas**
<p>Podemos consultar las imágenes creadas para la instalación de SFTP, con el comando...</p>


***2.1 Instalando el paquete vsftpd***


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

<p>Ahora probaremos a acceder desde un cliente como Filezilla, primeramente lo instalaremos con el comando.. </p>

> sudo apt install filezilla

![8](https://user-images.githubusercontent.com/73592097/146680390-980b3aa7-29f0-4a0f-9f2f-2c281cfc1e59.png)

<p>Accederemos al terminal, introducimos el siguiente comando para acceder a nuestro cliente filezilla</p>

> filezilla

![10](https://user-images.githubusercontent.com/73592097/146680555-b45159f1-6644-4789-b2a6-8e5f38ed6e56.png)

![14](https://user-images.githubusercontent.com/73592097/146680556-72710522-26e1-49ec-b6bc-df77a91fee21.png)

<p>A continuación nos conectaremos, introduciendo el servidor, usuario y contraseña</p>

![ftp](https://user-images.githubusercontent.com/73592097/146680662-ece2ef41-2a1b-479e-9ba0-ebed3d37245c.png)

![ee](https://user-images.githubusercontent.com/73592097/146680758-ab64bd22-c353-49e9-aba8-ceaee75ccbae.png)

**4. Configurar el servidor FTP**

<p>Incluso si accedemos desde una máquina Windows sin firewall, aunque con el cliente de consola podríamos acceder sin problemas, al tratar de acceder desde navegadores como Google Chrome la operación debería fallar.</p>
<p>Por lo tanto configurar el modo pasivo del servidor FTP en Ubuntu será útil para muchos escenarios. Para ello editaremos vsftpd.conf con el siguiente comando..</p>

<p>Añadiremos las siguientes directivas al final del archivo de configuración:</p>

> pasv_enable=YES
> pasv_min_port=30000
> pasv_max_port=30050

![con](https://user-images.githubusercontent.com/73592097/146681327-9a524ffc-35b8-4e93-9218-1f68716fb502.png)

<p>Terminada la configuración, guardamos los cambios y recargamos la configuración del servicio:</p>

![1](https://user-images.githubusercontent.com/73592097/146681510-5a416926-b75b-4ee8-a822-29061e87ab4e.png)

<p>Si el servidor Ubuntu tiene activado el firewall UFW, habrá que permitir el acceso al rango de puertos que acabamos de configurar:</p>

![2](https://user-images.githubusercontent.com/73592097/146681511-000c8e1c-edbb-4d03-bfb3-a4f04eec566a.png)

<p>Ahora verificamos el acceso desde el terminal</p>

![Captura de pantalla de 2021-12-19 15-04-47](https://user-images.githubusercontent.com/73592097/146679985-aea8db44-04c2-407f-be57-5ba451c00bad.png)


<p>Probamos a verificar el acceso desde el cliente filezilla</p>

<p>Introduciendo el puerto no conecta con el servidor</p>

![5](https://user-images.githubusercontent.com/73592097/146681688-3bbdc491-a1cd-449c-9aef-c7610eb1680f.png)

<p>Introduciendo el servidor, usuario, contraseña no conecta con el servidor</p>

![6](https://user-images.githubusercontent.com/73592097/146681689-bf6bb76c-bc44-4c46-91d1-c9cc660a76d9.png)

<p> Acceso de usuarios del sistema Por defecto el servidor FTP vsFTPd trabaja con los usuarios del sistema, que deberán autenticarse debidamente para acceder al servicio. Si sólo quieres usuarios anónimos podrás desactivar el acceso a usuarios del sistema modificando la directiva local_enable, donde cambiaremos yes por no. Pero si deseas mantenerlos hay ciertos ajustes que pueden ser interesantes, como que los usuarios locales puedan escribir en sus directorios</p>


<p>Descomentando la directiva write_enable manteniendo el valor YES los usuarios podrán crear o eliminar archivos y directorios</p>

![11](https://user-images.githubusercontent.com/73592097/146682574-255201b4-a90b-4634-8ca1-012382270672.png)

<p>Activaremos otra caracteristica para que los usuarios locales pueden navegar por todo el sistema de archivos de Ubuntu, cuando podría ser más interesante que solamente pudieran acceder a sus directorios personales.</p>

<p>Esta característica no se puede activar si la raíz del directorio personal (es decir, el directorio /home/usuario) es escribible, para evitar eliminar archivos o directorios esenciales, así que o cambiamos los permisos de estos directorios (como ocurre en servicios de hosting, por ejemplo), o añadimos la directiva allow_writeable_chroot</p>


![9](https://user-images.githubusercontent.com/73592097/146682572-7ee002df-3a28-4b79-9e71-15c9c43ff574.png)


<hr/>

Enlace github: <a href="https://github.com/joel92MM/Git/tree/main/2ºTrimestre/Instalacion_Administracion_Servidores_Transferencia_Archivos_Docker">enlace</a>
