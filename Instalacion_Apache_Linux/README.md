**Editando Readme**

![Captura de pantalla 2021-10-05 a las 18 14 52](https://user-images.githubusercontent.com/73592097/136071240-b94a632d-9a99-44ef-949c-d6a9b618104f.png)

**Índice**
<br/>
<hr/>

***1.	Requisitos previos para la instalación***

***2. Pasos para realizar la instalación***

***2.1 Actualización de los repositorios***

***2.2 Instalación de Apache***

***2.3 Acceso***

<hr/>

Requisitos previos 

Necesitara un servidor Ubuntu 20.04 con una cuenta de superusuario o root. Habilitar los puertos necesarios para el servicio apache.

Pasos para realizar la instalación en local

Actualización de los repositorios 

En primer lugar, actualizamos tanto los repositorios como el sistema operativo con el comando que se muestra en la imagen….

![Captura de pantalla 2021-10-05 a las 16 53 37](https://user-images.githubusercontent.com/73592097/136071781-53e39555-0470-44db-8ef9-fe87a0cbccb8.png)

Instalacion de Apache

En la terminal ejecutamos el siguiente comando…


![Captura de pantalla 2021-10-05 a las 17 01 11](https://user-images.githubusercontent.com/73592097/136071901-50f5c3d6-c263-4396-8a5b-6d660e07cdcd.png)

Si nos encontramos con un problema similar al siguiente...

![image](https://user-images.githubusercontent.com/73592097/136072067-33601fcb-0a50-4005-99e4-b35441692fb3.png)

Debemso realizar los siguientes cambios...

![image](https://user-images.githubusercontent.com/73592097/136072224-079476d5-a778-4b6e-96b1-8270504b0a46.png)

cambiamos listen 80 a listen 8081....

![image](https://user-images.githubusercontent.com/73592097/136072234-a4f2bd4e-182b-4db3-b0d5-b751dd28d97f.png)

Seguidamente ejecutamos el comando para reiniciar los servicios...

![image](https://user-images.githubusercontent.com/73592097/136072350-658889e9-ce32-4448-af6b-237ed98cc205.png)

![image](https://user-images.githubusercontent.com/73592097/136072378-45828765-3638-43de-8dac-fcbf39d6631b.png)

A continuación ajustamos la configuración del Firewall....

![image](https://user-images.githubusercontent.com/73592097/136072412-b4845499-e6a6-4a00-9a0d-be3e64d6293d.png)

Hasta finalizar con un mensaje similar a:

![image](https://user-images.githubusercontent.com/73592097/136072531-b17058a1-5e14-4170-8a90-c6a5f4927faf.png)

Usaremos el perfil Apache...

![image](https://user-images.githubusercontent.com/73592097/136072556-ac88c6dd-047a-4949-bab8-bb8813667b98.png)

Luego verificaremos los perfiles activos..

![image](https://user-images.githubusercontent.com/73592097/136072577-fe6f3b1b-e9cd-4f24-ac75-2076c3828d87.png)

Ahora verificamos que el servicio Apache este ejecutándose correctamente con el comando:

![image](https://user-images.githubusercontent.com/73592097/136072634-74c449cc-5280-4706-aab6-af552db10bd7.png)

Acceso 

Accedemos a nuestro navegador y ponemos la siguiente url que tenemos en la imagen anterior...

![image](https://user-images.githubusercontent.com/73592097/136072700-e8a33b00-6152-4f2b-84df-23b6efbcce14.png)



