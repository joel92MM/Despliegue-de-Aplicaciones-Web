<img src="https://user-images.githubusercontent.com/73592097/135727888-2c385e01-f09e-41bc-b21a-fe7a1c571568.png" alt="Portada">
<br/>
<hr/>

**Índice**

*****1.1 Mostrar el historial de cambios del repositorio*****


*****1.2 Crear la carpeta capítulos y crear dentro de ella el fichero capitulo1.txt con el texto siguiente:*****

> Git es un sistema de control de versiones ideado por Linus Torvalds.


*****1.3 Añadir los cambios a la zona de intercambio temporal.*****


*****1.4 Hacer commit de los cambios con el mensaje Añadido capítulo 1.*****


*****1.5 Volver a mostrar el historial de cambios del repositorio.*****


*****2.1 Crear el fichero capitulo2.txt en la carpeta capítulos con el siguiente texto.*****

> El flujo de trabajo básico con Git consiste en: <br/>
  > 1- Hacer cambios en el repositorio. <br/>
  > 2- Añadir los cambios a la zona de intercambio temporal. <br/>
  > 3- Hacer un commit de los cambios.<br/>



*****2.2  Añadir los cambios a la zona de intercambio temporal*****

*****2.3  Hacer un commit de los cambios con el mensaje Añadido capitulo 2.*****

*****2.4  Mostrar las diferencias entre la ultima y dos versiones anteriores*****

*****3.1  Crear el fichero capitulo3.txt en la carpeta capítulos con el siguiente texto.*****

> Git permite la creación de ramas lo que permite tener distintas versiones del mismo proyecto y trabajar de manera simultanea en ellas.

*****3.2 Añadir los cambios a la zona de intercambio temporal*****

*****3.3 Hacer un commit de los cambios con el mensaje Añadido capitulo 3.*****

*****3.4 Mostrar las diferencias entre la primera y la ultima versión del repositorio*****

*****4.1 Crear el fichero indice.txt en la siguiente línea*****

> Índice de los capítulos, con conceptos avanzados de git.

*****4.2 Añadir los cambios a la zona de intercambio temporal*****

*****4.3 Hacer un commit de los cambios con el mensaje "Índice de los capítulos, con conceptos avanzados de git.”*****

*****4.4 Mostrar quien ha hecho cambios sobre el fichero índice.txt*****

*****5.1 Crear una nueva rama bibliografía y mostrar las ramas del repositorio.*****

*****6.1 Crear el fichero capítulos/capitulo4.txt el texto siguiente:*****

> En este capítulo veremos cómo usar GitHub para alojar repositorios en remoto.

*****6.2 Añadir los cambios a la zona de intercambio temporal.*****

*****6.3 Hacer un commit de los cambios con el mensaje Añadido capitulo 4*****

*****6.4 Mostrar la historia del repositorio incluyendo todas las ramas*****

*****7.1 Cambiar a la rama bibliografia*****

*****7.2 Crear el fichero bibliografia.txt y añadir la siguiente referencia:*****

> Chacon, S. and Straub, B. Pro Git. Apress.

*****7.3 Añadir los cambios a la zona de intercambio temporal.*****

*****7.4 Hacer un commit de los cambios con el mensaje Añadida primera referencia bibliografica*****

*****7.5 Mostrar la historia del repositorio incluyendo todas las ramas*****

*****8.1 Fusionar la rama bibliografía con la rama main.*****

*****8.2 Mostrar la historia del repositorio incluyendo todas las ramas.*****

*****8.3 Eliminar la rama bibliografía.*****

*****8.4 Mostrar de nuevo la historia del repositorio incluyendo todas las ramas.*****

*****9.1 Crear la rama bibliografia*****

*****9.2 Cambiar a la rama bibliografía.*****

*****9.3 Cambiar el fichero bibliografia.txt para que contenga las siguientes referencias:*****

> Scott Chacon and Ben Straub. Pro Git. Apress.

> Ryan Hodson. Ry’s Git Tutorial. Smashwords (2014)

*****9.4 Cambiar a la rama main.****

*****9.5 Cambiar el fichero bibliografia.txt para que - contenga las siguientes referencias:*****

> Chacon, S. and Straub, B. Pro Git. Apress.

> Loeliger, J. and McCullough, M. Version control with Git. O’Reilly

*****9.6 Añadir los cambios a la zona de intercambio temporal y hacer un commit con el mensaje “Añadida nueva referencia bibliográfica.”****

*****9.7 Fusionar la rama bibliografía con la rama main.****

*****9.8 Resolver el conflicto dejando el fichero bibliografia.txt con las referencias:*****

> Chacon, S. and Straub, B. Pro Git. Apress.

> Loeliger, J. and McCullough, M. Version control with Git. O’Reilly.

*****9.9 Añadir los cambios a la zona de intercambio temporal y hacer un commit con el mensaje “Resuelto conflicto de bibliografía.”*****

*****9.10 Mostrar la historia del repositorio incluyendo todas las ramas.*****
<br/>
<br/>
<hr/>

******<p>Para hacer estos ejercicios es necesario haber hecho antes los ejercicios sobre historial de 
cambios o bien hacer un clon del repositorio remoto https://github.com/jpexposito/libro mediante la siguiente secuencia de comandos:</p>******
> git clone https://github.com/jpexposito/libro.git<br/>
> cd libro <br/>

<img src="https://user-images.githubusercontent.com/73592097/135731150-66223c19-0f27-4748-b9f5-5af54c5b4b39.png" alt="clonacion de git ">
<img src="https://user-images.githubusercontent.com/73592097/135731151-07d403a7-f4ea-481e-9153-b0a777472c9f.png" alt="entrando en la carpeta libro">

<hr/>

*****1.1 Mostrar el historial de cambios del repositorio*****

*****1.2 Crear la carpeta capítulos y crear dentro de ella el fichero capitulo1.txt con el texto siguiente:*****

> Git es un sistema de control de versiones ideado por Linus Torvalds.

*****1.3 Añadir los cambios a la zona de intercambio temporal.*****

*****1.4 Hacer commit de los cambios con el mensaje Añadido capítulo 1.*****

*****1.5 Volver a mostrar el historial de cambios del repositorio.*****

<img src="https://user-images.githubusercontent.com/73592097/135731152-b0580013-81fe-4347-9292-349a933e70b8.png" alt="Mostrando los pasos descritos anteriormente ">

<br/>
<hr/>

*****2.1 Crear el fichero capitulo2.txt en la carpeta capítulos con el siguiente texto.*****

> El flujo de trabajo básico con Git consiste en: <br/>
  > 1- Hacer cambios en el repositorio. <br/>
  > 2- Añadir los cambios a la zona de intercambio temporal. <br/>
  > 3- Hacer un commit de los cambios.<br/>
  
<img src="https://user-images.githubusercontent.com/73592097/135731329-0c11c118-4e7f-4e64-8390-4b5bdd4251db.png" alt="Creacion de fichero">


*****2.2  Añadir los cambios a la zona de intercambio temporal*****

*****2.3  Hacer un commit de los cambios con el mensaje Añadido capitulo 2.*****
<img src="https://user-images.githubusercontent.com/73592097/135731330-6256a7b1-8c68-4d98-b8e3-25a10f663b5b.png" alt="Haciendo commit">




*****2.4  Mostrar las diferencias entre la ultima y dos versiones anteriores*****
<img src="https://user-images.githubusercontent.com/73592097/135731331-4eb0858a-1323-417d-a4b7-f9568dd0e450.png" alt="Mostrando diferencias">


<br/>
<hr/>

*****3.1  Crear el fichero capitulo3.txt en la carpeta capítulos con el siguiente texto.*****

> Git permite la creación de ramas lo que permite tener distintas versiones del mismo proyecto y trabajar de manera simultanea en ellas.

<img src="https://user-images.githubusercontent.com/73592097/135731388-0eb03a19-e7ab-476a-8228-74893ba38e1d.png" alt="Creando archivo">


*****3.2 Añadir los cambios a la zona de intercambio temporal*****

*****3.3 Hacer un commit de los cambios con el mensaje Añadido capitulo 3.*****

<img src="https://user-images.githubusercontent.com/73592097/135731390-c417fc3d-d5d7-4b8e-a325-d1548985a1c0.png" alt="Haciendo commit">


*****3.4 Mostrar las diferencias entre la primera y la ultima versión del repositorio*****

<img src="https://user-images.githubusercontent.com/73592097/135731392-f27f4406-d7da-4852-ba3c-bfc2d51d9c8f.png" alt="Mostrando las diferencias de cambios">

<br/>
<hr/>

*****4.1 Crear el fichero indice.txt en la siguiente línea*****

> Índice de los capítulos, con conceptos avanzados de git.

*****4.2 Añadir los cambios a la zona de intercambio temporal*****

*****4.3 Hacer un commit de los cambios con el mensaje "Índice de los capítulos, con conceptos avanzados de git.”*****

*****4.4 Mostrar quien ha hecho cambios sobre el fichero índice.txt*****
<img src="https://user-images.githubusercontent.com/73592097/135731812-3ff6fb78-b510-4cd6-b19b-f91ebb1de114.png" alt="Muestra de resultados">

<br/>
<hr/>

*****5.1 Crear una nueva rama bibliografía y mostrar las ramas del repositorio.*****

<img src="https://user-images.githubusercontent.com/73592097/135731813-c74b4e0c-7864-4140-ba56-d1850ad067ce.png" alt="Creando una nueva rama">

<br/>
<hr/>

*****6.1 Crear el fichero capítulos/capitulo4.txt el texto siguiente:*****

> En este capítulo veremos cómo usar GitHub para alojar repositorios en remoto.

*****6.2 Añadir los cambios a la zona de intercambio temporal.*****

<img src="https://user-images.githubusercontent.com/73592097/135732335-e6f3be64-3e17-4928-8281-57f392a013a5.png" alt="Añadiendo cambios">


*****6.3 Hacer un commit de los cambios con el mensaje Añadido capitulo 4*****

<img src="https://user-images.githubusercontent.com/73592097/135732337-5038d198-1ccf-433c-b00e-9fe7d7cb031e.png" alt="Haciendo commit">


*****6.4 Mostrar la historia del repositorio incluyendo todas las ramas*****

<img src="https://user-images.githubusercontent.com/73592097/135732338-00217e6e-0852-47d8-9e30-c405fb6b9f3c.png" alt="Mostrando el historial">

<br/>
<hr/>

*****7.1 Cambiar a la rama bibliografia*****

<img src="https://user-images.githubusercontent.com/73592097/135732471-022d36b9-5f44-4d6f-96f4-382776d1dbae.png" alt="Cambiando la rama">


*****7.2 Crear el fichero bibliografia.txt y añadir la siguiente referencia:*****

> Chacon, S. and Straub, B. Pro Git. Apress.

<img src="https://user-images.githubusercontent.com/73592097/135732472-ae7f8db8-437d-439e-a02c-b7fe97fe5f55.png" alt="Creando fichero">


*****7.3 Añadir los cambios a la zona de intercambio temporal.*****

*****7.4 Hacer un commit de los cambios con el mensaje Añadida primera referencia bibliografica*****

<img src="https://user-images.githubusercontent.com/73592097/135732473-b46b4cfb-63f9-49ce-b777-e4943876f842.png" alt="Haciendo commit">

*****7.5 Mostrar la historia del repositorio incluyendo todas las ramas*****

<img src="https://user-images.githubusercontent.com/73592097/135732474-1f615074-431d-4ffb-9aff-6403d7b264c2.png" alt="Mostrando el historial">

<br/>
<hr/>

*****8.1 Fusionar la rama bibliografía con la rama main.*****

<img src="https://user-images.githubusercontent.com/73592097/135732476-8e583626-c6aa-4bd6-9e4b-983d1c7475d7.png" alt="Fusionando ramas">


*****8.2 Mostrar la historia del repositorio incluyendo todas las ramas.*****
<img src="https://user-images.githubusercontent.com/73592097/135732477-0d7a6e9c-bfc4-459d-9d07-a9214f794510.png" alt="Mostrando el historial ">
<img src="https://user-images.githubusercontent.com/73592097/135732478-b9c673a6-9eaf-4df6-bd9a-b5b4dcb9ddc9.png" alt="Mostrando el historial2 ">


*****8.3 Eliminar la rama bibliografía.*****

<img src="https://user-images.githubusercontent.com/73592097/135732479-573163a1-dcf8-4c1e-9678-0788e0d2c0e5.png" alt="eliminando ramas">


*****8.4 Mostrar de nuevo la historia del repositorio incluyendo todas las ramas.*****

<img src="https://user-images.githubusercontent.com/73592097/135732480-2e232bc1-a86c-4364-82ba-e829576c5221.png" alt="Mostrando el hisrotial del repositorio con los cambios">

<br/>
<hr/>

*****9.1 Crear la rama bibliografia*****

<img src="https://user-images.githubusercontent.com/73592097/135732769-5ede5ba9-9f74-4a72-9523-fe77d267c6c1.png" alt="Creacion de una rama">


*****9.2 Cambiar a la rama bibliografía.*****

<img src="https://user-images.githubusercontent.com/73592097/135732770-67001a70-88c2-40a9-a428-ce7f2771b116.png" alt="Cambiando rama">


*****9.3 Cambiar el fichero bibliografia.txt para que contenga las siguientes referencias:*****

> Scott Chacon and Ben Straub. Pro Git. Apress.

> Ryan Hodson. Ry’s Git Tutorial. Smashwords (2014)

<img src="https://user-images.githubusercontent.com/73592097/135732771-eeccd6df-4f54-49ee-bec1-f0ba3f69c5d6.png" alt="Cambiando el contenido del fichero">
<img src="https://user-images.githubusercontent.com/73592097/135732772-e3afe470-3b18-4a0e-abed-41fcc50c50c7.png" alt="haciendo commin">

*****9.4 Cambiar a la rama main.*****

<img src="https://user-images.githubusercontent.com/73592097/135732773-062957a8-2fb6-493d-a0a5-e552a892eda4.png" alt="Cambiando a la rama main">


*****9.5 Cambiar el fichero bibliografia.txt para que - contenga las siguientes referencias:*****

> Chacon, S. and Straub, B. Pro Git. Apress.

> Loeliger, J. and McCullough, M. Version control with Git. O’Reilly.

<img src="https://user-images.githubusercontent.com/73592097/135732774-b458ed45-a764-421d-bfee-1504cb4abe1b.png" alt="Cambiando fichero">
<img src="https://user-images.githubusercontent.com/73592097/135732775-70bb0965-2f0b-4e0b-91ef-842c09ed925a.png" alt="Añadiendo cambios">



*****9.6 Añadir los cambios a la zona de intercambio temporal y hacer un commit con el mensaje “Añadida nueva referencia bibliográfica.”*****

<img src="https://user-images.githubusercontent.com/73592097/135732776-16396395-29e4-4870-9ec5-464a20298754.png" alt="Fusionando ramas">

*****9.7 Fusionar la rama bibliografía con la rama main.*****

<img src="https://user-images.githubusercontent.com/73592097/135732777-3d53de99-da7b-436b-8aef-804a0f961e4c.png" alt="Fusionando ramas">


*****9.8 Resolver el conflicto dejando el fichero bibliografia.txt con las referencias:*****

> Chacon, S. and Straub, B. Pro Git. Apress.

> Loeliger, J. and McCullough, M. Version control with Git. O’Reilly.

*****9.9 Añadir los cambios a la zona de intercambio temporal y hacer un commit con el mensaje “Resuelto conflicto de bibliografía.”*****

<img src="https://user-images.githubusercontent.com/73592097/135732778-7e1f7439-a4a0-4b06-8b0a-47e79be43541.png" alt="Añadiendo cambios">


*****9.10 Mostrar la historia del repositorio incluyendo todas las ramas.*****

<img src="https://user-images.githubusercontent.com/73592097/135732779-cb1ba531-4ef7-46ed-bd04-03b45f25b656.png" alt="Mostral el hisrotial de repositorio con los cambios">
