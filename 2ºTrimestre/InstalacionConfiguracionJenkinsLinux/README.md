<img alt="README-8d1790bc.png" src="assets/README-8d1790bc.png" width="" height="" >
<hr/>

# Índice #

## 1. Requisitos básicos ##

## 2. Instalar Jenkins ##

## 3. Iniciar Jenkins ##

## 4. Abrir el Firewall ##

## 5. Configurar Jenkins ##


<hr/>

**1. Requisitos básicos**

- Disponer de una máquina Ubuntu 20.04
- Internet
- Open JDK 11

**2. Instalar Jenkins**

<p>Primero, agregamos la clave del repositorio al sistema:</p>

<p>Unaa vez agregada la clave, el sistema devolvera como resultado ok</p>


>   wget -q -O - https://pkg.jenkins.io/debian-stable/jenkins.io.key | sudo apt-key add

<img alt="README-24d7e545.png" src="assets/README-24d7e545.png" width="" height="" >

<p>A continuación, vamos a anexar la dirección del repositorio de paquetes de Debian a sources.list del servidor:

</p>

>  sudo sh -c 'echo deb http://pkg.jenkins.io/debian-stable binary/ > /etc/apt/sources.list.d/jenkins.list'


<img alt="README-69daed37.png" src="assets/README-69daed37.png" width="" height="" >


<p>Una vez que se hayan ingresado ambos comandos, ejecutaremos update de manera que apt utilice el nuevo repositorio. REALIZA ESTE PASO SÓLO SI HAY MUCHO TIEMPO QUE NO ACTUALIZAS EL SISTEMA, O TIENES PROBLEMAS EN EL SIGUIENTE PASO.</p>

> sudo apt update

<img alt="README-61242d30.png" src="assets/README-61242d30.png" width="" height="" >

<p>Ahora instalaremos Jenkis y sus dependencias, con el comando </p>

> sudo apt install Jenkins

<img alt="README-512e2e9b.png" src="assets/README-512e2e9b.png" width="" height="" >

<p>Posteriormente iniciamos el servidor de Jenkins</p>
<p></p>
<p></p>
<p></p>
<p></p>
<p></p>
<p></p>
<p></p>
<p></p>
<p></p>
<p></p>
<p></p>
<p></p>
<p></p>
<p></p>
<p></p>
<p></p>
<p></p>
<p></p>
<p></p>
<p></p>
<p></p>
<p></p>
