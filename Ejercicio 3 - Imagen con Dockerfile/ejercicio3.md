# TAREA EVALUABLE 3 - SEGUNDA EVALUACIÓN
**Autor: Mauro Fernández Vegas**

**Fecha: 010/04/2023**

Despliegue de aplicaciones Web - CIFP La laboral 2022/2023

##  Ejercicio 3 - Imagen con Dockerfile

Para crear una imagen de docker yo mismo primero voy a preparar una carpeta con los archivos necesarios que va a utilizar mi aplicación. En este caso va a ser una carpeta que contiene una plantilla con html y css y un documento Dockerfile.

![](capturas/Captura1.JPG)

El documento Dockerfile cambia en función de en que basemos nuestra imagen. Para saber como crearlo correctamente hay que acudir a docker-hub y ver la documentación, en mi caso de nginx.

![](capturas/Captura2.JPG)

En esta sección está lo que necesito.

![](capturas/Captura3.JPG)

Ya tengo la carpeta con todos los archivos que voy a utilizar listos. Ahora voy a crear mi imagen.
Nota: primero hay que situarse en la carpeta donde se encuentran los archivos Dockerfile y la plantilla, en mi caso o un index.html.

![](capturas/Captura4.JPG)

Y ahora creo la imagen.

```bash
docker build -t fvmauro/ejercicio3:v1 .
```
![](capturas/Captura5.JPG)

Compruebo que se ha creado la imagen

![](capturas/Captura6.JPG)

Ahora voy a crear un contenedor que utilice mi imagen.
```bash
docker run -d -p 4321:80 --name entregable fvmauro/ejercicio3:v1
```
![](capturas/Captura7.JPG)

Compruebo el contenedor.

![](capturas/Captura8.JPG)

En un principio parece que esta todo correcto. Abro el navegador y voy a la URL: `localhost:4321:80` para comprobar que todo funciona bien.

![](capturas/Captura9.JPG)

Como muestro en la captura, todo esta perfecto. La imagen funciona correctamente así que he decidido compartirla con todo el mundo.
Voy a compartirla en mi cuenta de docker-hub.

```bash
docker login
```
![](capturas/Captura10.JPG)

Una vez conectado a mi cuenta solo tengo que realizar un push.

```bash
docker push fvmauro/ejercicio3:v1
```
![](capturas/Captura11.JPG)

Todo parece correcto. Voy a comprobarlo en docker-hub.

![](capturas/Captura12.JPG)

Efectivamente, aquí esta. Ahora cualquier persona puede descargarse mi aplicacion con el siguiente comando: `docker pull fvmauro/ejercicio3`

![](capturas/Captura13.JPG)

## WEBGRAFÍA

1. <a href="https://hub.docker.com/" target="_blank">https://hub.docker.com/</a>


