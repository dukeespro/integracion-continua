# Integración Continua!

Este es un proyecto para la clase de integración continua de la universidad Poli. Se creo un proyecto ASP NET Core con Docker y Docker-Compose para la orquestación de los contenedores. Cabe la posibilidad de usar Podman o Containerd para el servicio del demonio.


## Requerimientos
- Un computador con Docker instalado, puede ser Windows, Linux o MacOS.
- Tener instalado Docker-compose.
- Acceso al repositorio Git

## Arquitectura

![Arquitectura de contenedores](https://i.ibb.co/ys3ysxJ/integracion-continua.jpg)

## Correr el programa

- Primero debemos clonar el repositorio.
````bash
git clone https://github.com/dukeespro/integracion-continua.git
````
- Entramos a la carpeta del repositorio.
````bash
cd integracion-continua
````
- Corremos el docker-compose. Esto va a generar el build de las imagenes.
````bash
docker-compose up -d
````
- Ver las imagenes corriendo
````bash
docker ps

CONTAINER ID  IMAGE                                              COMMAND     CREATED      STATUS            PORTS                 NAMES
fc6ef679b96a  localhost/integracion-continua_webfrontend:latest              9 hours ago  Up 6 seconds ago  0.0.0.0:8080->80/tcp  webfrontend
674243a1564c  docker.io/library/mysql:8.0                        mysqld      9 hours ago  Up 9 hours ago                          db
````
- Ingresamos al aplicativo web con un navegador, el cual esta publico en el puerto 8080. Recuerden que si lo vamos a consultar desde nuestro equipo, debemos usar la IP 127.0.0.1 o localhost. Por ejemplo desde nuestro equipo:
````bash
http://127.0.0.1:8080
````
