<img alt="README-8d1790bc.png" src="assets/README-8d1790bc.png" width="" height="" >
<hr/>

# Índice #

## 1. Requisitos básicos ##

## 2. Creación del dominio ##

## 3. Instalar Jenkins ##

## 4. Iniciar Jenkins ##

## 5. Abrir el Firewall ##

## 6. Configurar Jenkins ##


<hr/>

**1. Requisitos básicos**

- Disponer de una máquina Ubuntu 20.04
- Internet
- Open JDK 11

**2. Creación del dominio**
<p>Nos situamos en la carpeta de apache sites-available</p>

<img alt="README-96d09888.png" src="assets/README-96d09888.png" width="800px"/>

<p>Copiamos la carpeta de original apache y creamos una nueva </p>

<img alt="README-64009b62.png" src="assets/README-64009b62.png" width="800px"/>

<p>Configuramos la carpeta nueva</p>

<img alt="README-5b8bc9b0.png" src="assets/README-5b8bc9b0.png" width="800px"/>

<p>Habilitamos el sitio</p>

<img alt="README-5913490e.png" src="assets/README-5913490e.png" width="800px"/>

<p>Reiniciamos apache</p>

<img alt="README-995ac3cb.png" src="assets/README-995ac3cb.png" width="800px"/>

<p>Añadimos el dominio en /etc/hosts</p>

<img alt="README-da0f2282.png" src="assets/README-da0f2282.png" width="800px"/>

**3. Instalar Jenkins**

<p>Primero, agregamos la clave del repositorio al sistema:</p>

<p>Unaa vez agregada la clave, el sistema devolvera como resultado ok</p>


>   wget -q -O - https://pkg.jenkins.io/debian-stable/jenkins.io.key | sudo apt-key add

<img alt="README-24d7e545.png" src="assets/README-24d7e545.png" width="800px"/>

<p>A continuación, vamos a anexar la dirección del repositorio de paquetes de Debian a sources.list del servidor:

</p>

>  sudo sh -c 'echo deb http://pkg.jenkins.io/debian-stable binary/ > /etc/apt/sources.list.d/jenkins.list'


<img alt="README-69daed37.png" src="assets/README-69daed37.png" width="800px"/>


<p>Una vez que se hayan ingresado ambos comandos, ejecutaremos update de manera que apt utilice el nuevo repositorio. REALIZA ESTE PASO SÓLO SI HAY MUCHO TIEMPO QUE NO ACTUALIZAS EL SISTEMA, O TIENES PROBLEMAS EN EL SIGUIENTE PASO.</p>

> sudo apt update

<img alt="README-61242d30.png" src="assets/README-61242d30.png" width="800px"/>

<p>Ahora instalaremos Jenkis y sus dependencias, con el comando </p>

> sudo apt install Jenkins

<img alt="README-512e2e9b.png" src="assets/README-512e2e9b.png" width="800px"/>

<p>Posteriormente iniciamos el servidor de Jenkins</p>

**4 . Iniciar Jenkins**

<p>Iniciamos Jenkins con el siguiente comando...</p>

> sudo systemctl start jenkins

<img alt="README-7e507351.png" src="assets/README-7e507351.png" width="800px"/>

<p>Verificamos que Jenkis se haya iniciado correctamente con el comando..</p>

> sudo systemctl status jenkins

<p>Resultado </p>

<img alt="README-9d05db79.png" src="assets/README-9d05db79.png" width="800px"/>

**5 . Abrir el Firewall**

<p>Configuramos el Firewall UFW, con el comando...</p>

> sudo ufw allow 8080

<img alt="README-a21f23e4.png" src="assets/README-a21f23e4.png" width="800px"/>

<p>Si esta desactivado ejecutaremos los siguientes comandos..</p>

> sudo ufw allow OpenSSH<br/>
> sudo ufw enable

<p>Compruebe el estado de ufw para confirmar las nuevas reglas, con el comando</p>

> sudo ufw status

<p>Resultado</p>

<img alt="README-48c68c3e.png" src="assets/README-48c68c3e.png" width="800px"/>

**6. Configurar Jenkins**


<p>En el navegador insertamos nuestro dominio y puerto para configurar Jenkins, deberia ver una imagen como la siguiente..</p>

<img alt="README-6bb0c395.png" src="assets/README-6bb0c395.png" width="800px"/>

<p>Para mostrar la contraseña utilizaremos el siguiente comando..</p>

> sudo cat /var/lib/jenkins/secrets/initialAdminPassword

<img alt="README-403b238f.png" src="assets/README-403b238f.png" width="800px"/>

<p>Copiamos la contraseña alfanumérica de 32 caracteres de la terminal, la pegamos y luego clickeamos en Continue.</p>

<img alt="README-ffd66b58.png" src="assets/README-ffd66b58.png" width="800px"/>

<p>Haremos clic en la opción Install suggested plugins (Instalar los complementos sugeridos), que iniciará de inmediato el proceso de instalación.</p>

<img alt="README-f958a74f.png" src="assets/README-f958a74f.png" width="800px"/>

<p>Espereamos que se complete el proceso de instalación</p>

<img alt="README-8d6e2c29.png" src="assets/README-8d6e2c29.png" width="800px"/>

<p>En la siguiente ventana configuramos el usuario administrador</p>


<img alt="README-70fdbd88.png" src="assets/README-70fdbd88.png" width="800px"/>


<p>Introduciendo nuestra informacion </p>

<img alt="README-0014f249.png" src="assets/README-0014f249.png" width="800px"/>

<p>Confirmamos la url para instanciar Jenkis</p>

<img alt="README-1aff64bf.png" src="assets/README-1aff64bf.png" width="800px"/>

<p>Finalizado el proceso de congifuracion se mostrara una ventan similar a la siguiente </p>
<img alt="README-6430e162.png" src="assets/README-6430e162.png" width="800px"/>

<p>Clickeamos en *Start using Jenkins* donde nos mostrara el panel de Jenkins</p>

<img alt="README-be14ed8c.png" src="assets/README-be14ed8c.png" width="800px"/>

<hr/>

Enlace github: <a href="https://github.com/joel92MM/Git/tree/main/2ºTrimestre/InstalacionConfiguracionJenkinsLinux">enlace</a>
