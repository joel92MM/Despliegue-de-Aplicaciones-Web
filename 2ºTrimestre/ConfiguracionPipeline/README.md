<img alt="README-e7c89d9c.png" src="assets/README-e7c89d9c.png" width="" height="" >
<hr/>

# Índice #

## 1. Requisitos básicos ##

## 2. Creación de Pipelines ##

- ### 2.1 Java ###
- ### 2.2 Node.js ###
- ### 2.3 Ruby ###
- ### 2.4 Python ###
- ### 2.5 PHP ###
- ### 2.6 GO ###


<hr/>

**1. Requisitos básicos**

- <p>Tener jenkins instalado</p>
- <p>Tener los contenedores de docker jenkins parados, para eso utilizamos el metodo cortar por lo sano paramos todos los contenedores docker y así no tenemos ningún tipo de problema con el comando </p>
<p>Si tenemos problemas de permisos ejecutaremos el siguiente comando</p>

<img alt="README-e6b81ecb.png" src="assets/README-e6b81ecb.png" width="800px"/>

<p>Luego los paramos</p>

<img alt="README-3702675b.png" src="assets/README-3702675b.png" width="800px"/>

<p>Posteriormente reiniciamos el servicio apache y jenkins</p>
<p>Luego reiniciamos nuestra máquina virtual</p>

<img alt="README-1d0682ec.png" src="assets/README-1d0682ec.png" width="800px"/>

**2. Creación del Pipelines**
<p>Accedemos a jenkins</p>

<img alt="README-af8bb5e3.png" src="assets/README-af8bb5e3.png" width="800px"/>

<p>Se mostraran los diferentes pasos para la creación de los tipos de lenguajes</p>
<hr/>


***2.1. Java***

<p>Creación de Pipeline en Java</p>

<p>Clickeamos en nueva tarea</p>

<img alt="README-cc6f4da5.png" src="assets/README-cc6f4da5.png" width="800px"/>

<p>Definimos el nombre del pipeline</p>

<img alt="README-da82337d.png" src="assets/README-da82337d.png" width="800px"/>

<p>En la opcion de pipeline, nos vamos a script y pegamos el script  de la siguiente imagen</p>

<img alt="README-46822063.png" src="assets/README-46822063.png" width="800px"/>

<p>Una vez guardado, pulsamos la opción construir ahora</p>

<img alt="README-be58fc19.png" src="assets/README-be58fc19.png" width="800px"/>

<p>Nos dara un error en el proceso</p>

<img alt="README-eb1de166.png" src="assets/README-eb1de166.png" width="800px"/>

<img alt="README-f1973705.png" src="assets/README-f1973705.png" width="800px"/>

<p>Este es el error que sale por consola </p>

<img alt="README-baecce51.png" src="assets/README-baecce51.png" width="800px"/>

### Solución del error ###

<p>Nos vamos al panel de control de jenkins, administrar jenkins</p>

<img alt="README-1479f94f.png" src="assets/README-1479f94f.png" width="800px"/>

<p>Nos vamos a la opción de administrar plugins</p>

<img alt="README-9aa51059.png" src="assets/README-9aa51059.png" width="800px"/>

<p>Nos vamos a la pestaña todos los plugins y en el cuadro de búsqueda introducimos docker, y seleccionamos las siguientes opciones</p>

<img alt="README-505e1381.png" src="assets/README-505e1381.png" width="800px"/>

<p>Pulsamos en descargar ahora e instalar después de reiniciar</p>

<p>Nos aparecerá una ventana similar a la siguiente, seleccionamos la opción de reiniciar jenkins cuando termine la instalación..</p>

<img alt="README-f964a18f.png" src="assets/README-f964a18f.png" width="800px"/>

<p>Nos aparecerá la siguiente ventana</p>

<img alt="README-58c5e155.png" src="assets/README-58c5e155.png" width="800px"/>

<p>Volvemos a pulsar la opción de construir ahora y se nos mostrará otro error distinto</p>

<img alt="README-c82c3741.png" src="assets/README-c82c3741.png" width="800px"/>

<p>Se muestra una ventana similar a la siguiente, de error de permisos</p>

<img alt="README-e8ebfe8f.png" src="assets/README-e8ebfe8f.png" width="800px"/>

<p>Añadimos permisos de usermod, con el comando...</p>

> sudo usermod -a -G docker jenkins

<img alt="README-5c7fb3f6.png" src="assets/README-5c7fb3f6.png" width="800px"/>

<p>Ahora nos vamos a la terminal para añadir el usuario de jenkins al grupo de sudoers</p>

<img alt="README-06ad5290.png" src="assets/README-06ad5290.png" width="800px"/>

<p>Reiniciamos los servicios de apache y de jenkins</p>

<img alt="README-b5b3f7d7.png" src="assets/README-b5b3f7d7.png" width="800px"/>

<p>Volvemos a ejecutar pipeline y vemos que se ejecuta</p>

<img alt="README-8f033d96.png" src="assets/README-8f033d96.png" width="800px"/>

<p>Ahora tenemos el pipeline de java instalado, hacemos el proceso con los siguientes lenguajes a instalar</p>


***2.2. Node.js***

<p>Creación de Pipeline en Node.js</p>
<p>Clickeamos en nueva tarea</p>

<img alt="README-cc6f4da5.png" src="assets/README-cc6f4da5.png" width="800px"/>

<p>Definimos el nombre del pipeline</p>

<img alt="README-e842212c.png" src="assets/README-e842212c.png" width="800px"/>

<p>En la opción de pipeline, nos vamos a script y pegamos el script  de la siguiente imagen</p>

<img alt="README-4ed410f8.png" src="assets/README-4ed410f8.png" width="800px"/>

<p>Una vez guardado, pulsamos la opción construir ahora</p>

<img alt="README-cfb0180d.png" src="assets/README-cfb0180d.png" width="800px"/>

<img alt="README-8f92d222.png" src="assets/README-8f92d222.png" width="800px"/>

<p>Finalmente se ha instalado el pipeline</p>

<img alt="README-52882074.png" src="assets/README-52882074.png" width="800px"/>


***2.3. Ruby***

<p>Creación de Pipeline en Ruby</p>
<p>Clickeamos en nueva tarea</p>

<img alt="README-cc6f4da5.png" src="assets/README-cc6f4da5.png" width="800px"/>

<p>Definimos el nombre del pipeline</p>

<img alt="README-f898b30c.png" src="assets/README-f898b30c.png" width="800px"/>


<p>En la opción de pipeline, nos vamos a script y pegamos el script  de la siguiente imagen</p>

<img alt="README-e3ad587a.png" src="assets/README-e3ad587a.png" width="800px"/>

<p>Una vez guardado, pulsamos la opción construir ahora</p>

<img alt="README-083e3e1c.png" src="assets/README-083e3e1c.png" width="800px"/>

<img alt="README-8bf44a00.png" src="assets/README-8bf44a00.png" width="800px"/>


<p>Finalmente se ha instalado el pipeline</p>

<img alt="README-39dca1c6.png" src="assets/README-39dca1c6.png" width="800px"/>

***2.4. Python***

<p>Creación de Pipeline en Python</p>
<p>Clickeamos en nueva tarea</p>

<img alt="README-cc6f4da5.png" src="assets/README-cc6f4da5.png" width="800px"/>

<p>Definimos el nombre del pipeline</p>

<img alt="README-34dcba6d.png" src="assets/README-34dcba6d.png" width="800px"/>

<p>En la opción de pipeline, nos vamos a script y pegamos el script  de la siguiente imagen</p>

<img alt="README-4f2e36eb.png" src="assets/README-4f2e36eb.png" width="800px"/>

<p>Una vez guardado, pulsamos la opción construir ahora</p>

<img alt="README-23787efa.png" src="assets/README-23787efa.png" width="800px"/>

<img alt="README-b0bd33e5.png" src="assets/README-b0bd33e5.png" width="800px"/>

<p>Finalmente se ha instalado el pipeline</p>

<img alt="README-8d3ee026.png" src="assets/README-8d3ee026.png" width="800px"/>

***2.5. PHP***

<p>Creación de Pipeline en PHP</p>
<p>Clickeamos en nueva tarea</p>

<img alt="README-cc6f4da5.png" src="assets/README-cc6f4da5.png" width="800px"/>

<p>Definimos el nombre del pipeline</p>

<img alt="README-3e4a48cc.png" src="assets/README-3e4a48cc.png" width="800px"/>

<p>En la opción de pipeline, nos vamos a script y pegamos el script  de la siguiente imagen</p>

<img alt="README-5c6b2b5c.png" src="assets/README-5c6b2b5c.png" width="800px"/>

<p>Una vez guardado, pulsamos la opción construir ahora</p>

<img alt="README-058bcb13.png" src="assets/README-058bcb13.png" width="800px"/>

<img alt="README-7184bdda.png" src="assets/README-7184bdda.png" width="800px"/>

<p>Finalmente se ha instalado el pipeline</p>

<img alt="README-8f8dd5e2.png" src="assets/README-8f8dd5e2.png" width="800px"/>

***2.6. GO***

<p>Creación de Pipeline en GO</p>
<p>Clickeamos en nueva tarea</p>

<img alt="README-cc6f4da5.png" src="assets/README-cc6f4da5.png" width="800px"/>

<p>Definimos el nombre del pipeline</p>

<img alt="README-0d42167e.png" src="assets/README-0d42167e.png" width="800px"/>

<p>En la opción de pipeline, nos vamos a script y pegamos el script  de la siguiente imagen</p>

<img alt="README-ff19c61a.png" src="assets/README-ff19c61a.png" width="800px"/>

<p>Una vez guardado, pulsamos la opción construir ahora</p>

<img alt="README-c67c180f.png" src="assets/README-c67c180f.png" width="800px"/>

<img alt="README-0ccfa6a3.png" src="assets/README-0ccfa6a3.png" width="800px"/>


<p>Finalmente se ha instalado el pipeline</p>

<img alt="README-8e1edbdb.png" src="assets/README-8e1edbdb.png" width="800px"/>


<p>Se muestran los distintos lenguajes instalados en jenkins pipeline</p>

<img alt="README-2498b0b8.png" src="assets/README-2498b0b8.png" width="800px"/>


<hr/>

Enlace github: <a href="https://github.com/joel92MM/Git/tree/main/2ºTrimestre/ConfiguracionPipeline">enlace</a>
