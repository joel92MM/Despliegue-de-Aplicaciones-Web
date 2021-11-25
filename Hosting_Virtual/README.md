<img alt="README-6024d7b4.png" src="assets/README-6024d7b4.png" width="" height="" >
<hr/>
<br/>


<p>El servidor web Apache2 se instala por defecto con un host virtual. Su configuración esta..</p>

> /etc/apache2/sites-available/000-default.conf

<p>Construimos dos nombres de dominio </p>

> www.iespuerto.org
> www.departamentospuerto.org

<p>Donde el directorio base sera </p>

> /var/www/nombre_directorio

<img alt="README-1cfb97b3.png" src="assets/README-1cfb97b3.png" width="" height="" >

<p>Sus páginas web seran</p>

> index.html

<p>Contenido de la pagina </p>

>Bienvenid@ a la página del nombre_directorio

<p>Los ficheros de configuración de los sitios webs se encuentran en el directorio /etc/apache2/sites-available, por defecto hay dos ficheros, uno se llama 000-default.conf que es la configuración del sitio web por defecto. Necesitamos tener dos ficheros para realizar la configuración de los dos sitios virtuales, para ello vamos a copiar el fichero 000-default.conf</p>

> cd /etc/apache2/sites-available

> cp 000-default.conf iespuerto.conf

> cp 000-default.conf departamentos.conf

<p>Modificamos los ficheros iespuerto.conf y departamentos.conf, para indicar el nombre que vamos ausar para acceder al host virtual (ServerName) y el directorio detrabajo (DocumentRoot).</p>

<p>es necesario crear un enlace simbólico a estos ficheros dentro del directorio /etc/apache2/sites-enabled</p>

> a2ensite iespuerto
> a2ensite departamentos

<p>Si queremos deshabilitar los enlaces simbolicos usaremos</p>

>a2dissite nombre_dichero_configuracion

<p>Reiniciamos los servicios</p>
<p>Para finalizar cambiamos el fihero host en el cliente para introducir dos nuevas lineas donde haga conversacion nombre de dominio-> direccion de servidor</p>

<img alt="README-07623875.png" src="assets/README-07623875.png" width="" height="" >

<p>Tras esto paramso y inicializamos el servidor apache, y mostraremso las pagians web enel navegador</p>

<img alt="README-5734ba4a.png" src="assets/README-5734ba4a.png" width="" height="" >

<img alt="README-4b71acd0.png" src="assets/README-4b71acd0.png" width="" height="" >
