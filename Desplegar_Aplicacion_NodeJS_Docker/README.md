<img alt="README-0c8e70fe.png" src="assets/README-0c8e70fe.png" width="" height="" >


<br/>
<hr/>

# Índice #

## 1. Crear la aplicación Node.js ##
## 2. Creando un Dockerfile##
## 3. Construyendo la imagen##
## 4. Ejecutando la imagen##
## 5. Probando la imagen##

<hr/>

**1. Crear la aplicacion Node.JS**

<p>Antes de nada actualizaremos nuestro repositorio de paquetes, con el comando..</p>

> sudo apt update && apt upgrade

<img alt="README-92668f53.png" src="assets/README-92668f53.png" width="800px"/>

<p>Seguidamente instalaremos un gestor de paquetes con los siguientes comandos</p>

> curl -fsSL https://deb.nodesource.com/setup_lts.x | sudo -E bash -

> sudo apt-get install -y nodejs

<img alt="README-e4c6231a.png" src="assets/README-e4c6231a.png" width="800px"/>
<img alt="README-a2201380.png" src="assets/README-a2201380.png" width="800px"/>

<p>Comprobamos que esta instalado la version 8.1.0 con el siguiente comando</p>

> npm --version

<img alt="README-4ca9e8ef.png" src="assets/README-4ca9e8ef.png" width="800px"/>

<p>Primero nos crearemos un nuevo directorio donde estarán todos los archivos</p>

<img alt="README-09f34101.png" src="assets/README-09f34101.png" width="800px"/>

<p> posteriormente abriremos VSCODE, con la carpeta creada y dentro de ella crearemos el archivo *package.json* con el contenido siguiente </p>

* <p>{
  "name": "docker_web_app",<br/>

  "version": "1.0.0",<br/>

  "description": "Node.js on Docker",<br/>

  "author": "First Last <first.last@example.com>",<br/>

  "main": "server.js",<br/>

  "scripts": {<br/>

    "start": "node server.js"<br/>

  },<br/>

  "dependencies": {<br/>

    "express": "^4.16.1"<br/>

  }<br/>

}
</p>

<img alt="README-987fbbf1.png" src="assets/README-987fbbf1.png" width="800px"/>

<p>Ahora ejecutamos el comando siguiente, que nos generará un package-lock.json que se copiará a su imagen de Docker.</p>

> npm install

<img alt="README-3d1cacb8.png" src="assets/README-3d1cacb8.png" width="800px"/>

<p>Luego, cree un server.jsarchivo que defina una aplicación web usando el marco Express.js con el contenido siguiente</p>

* <p>
'use strict';<br/>


const express = require('express');<br/>


// Constants<br/>

const PORT = 8080;<br/>

const HOST = '0.0.0.0';<br/>


// App<br/>

const app = express();<br/>

app.get('/', (req, res) => {<br/>

  res.send('Hello World');<br/>

});<br/>


app.listen(PORT, HOST);<br/>

console.log(`Running on http://${HOST}:${PORT}`);<br/>
</p>

<img alt="README-5960a00d.png" src="assets/README-5960a00d.png" width="800px"/>

**2. Creando un Dockerfile**

<p>Creamos un archivo vacío llamado Dockerfile con el siguiente comando</p>

>touch Dockerfile

<p>Dentro del archivo escribiremos el siguiente contenido</p>

<img alt="README-c868b083.png" src="assets/README-c868b083.png" width="800px"/>

<p>Ahora crearemos un .dockerignore en el mismo directorio que el Dockerfile con el siguiente contenido:</p>

<img alt="README-009f1689.png" src="assets/README-009f1689.png" width="800px"/>

<p>Esto evitará que sus módulos locales y registros de depuración se copien en la imagen de Docker y posiblemente sobrescriban los módulos instalados dentro de su imagen.</p>

**3. Construyendo la imagen**

<p>Vamos al directorio que tiene Dockerfile y ejecutamos el siguiente comando para construir la imagen de Docker. La -t bandera permite etiquetar la imagen para que sea más fácil encontrarla más tarde usando el docker images el comando es </p>

> docker build . -t joel/node-web-app

<img alt="README-c0623bd4.png" src="assets/README-c0623bd4.png" width="800px"/>

<p>Listamos las imagenes de docker</p>

<img alt="README-58e9905c.png" src="assets/README-58e9905c.png" width="800px"/>

**4. Ejecutando la imagen**

<p> Crearemos un contenedor con la imagen creada anteriormente con el comando...</p>

> docker run -p 49160:8080 -d joel/node-web-app

<img alt="README-e67dfe6e.png" src="assets/README-e67dfe6e.png" width="800px"/>


<p>Obtenemos el ID del contenedor con el comando siguiente</p>

> sudo docker ps

<img alt="README-209ea070.png" src="assets/README-209ea070.png" width="800px"/>

<p>Obtenemos la salida de la aplicacion</p>

> sudo docker logs <container id>

<img alt="README-56affd81.png" src="assets/README-56affd81.png" width="800px"/>

<p>Ingresamos el contenedor con el comando</p>

>docker exec -it <container id> /bin/bash

<img alt="README-5cc9e6b5.png" src="assets/README-5cc9e6b5.png" width="800px"/>

**5. Probando la imagen**
<p>Ahora probamos la aplicación </p>

<p>Ingresamos en el navegador la siguiente dirección de la imagen </p>

<img alt="README-b7169f63.png" src="assets/README-b7169f63.png" width="800px"/>








<hr/>

Enlace github: <a href="https://github.com/joel92MM/Git/tree/main/Desplegar_Aplicacion_NodeJS_Docker">enlace</a>
