# Integración Continua!

Este es un proyecto para la clase de integración continua de la universidad Poli. Se creo un proyecto NPM NextJS con Docker y Docker-Compose para la orquestación de los contenedores. Cabe la posibilidad de usar Podman o Containerd para el servicio del demonio.

## Integrantes
Luis Eduardo Cuellar Rubio

## Requerimientos
- Un computador con Docker instalado, puede ser Windows, Linux o MacOS.
- Tener instalado Docker-compose.
- Acceso al repositorio Git

## Arquitectura

![Arquitectura de contenedores](https://i.ibb.co/cFDQYkT/integracion-continua-drawio.png)

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

CONTAINER ID  IMAGE                                              COMMAND        CREATED             STATUS             PORTS                   NAMES
e3c38f28781f  localhost/integracion-continua_webfrontend:latest  npm start      8 minutes ago       Up 8 minutes ago   0.0.0.0:3000->3000/tcp  webfrontend
24f74ade5a91  docker.io/library/mongo:latest                     mongod         About a minute ago  Up 49 seconds ago                          integracion-continua_mongo_1
cefe0ee4e651  docker.io/library/mongo-express:latest             mongo-express  51 seconds ago      Up 37 seconds ago  0.0.0.0:8081->8081/tcp  integracion-continua_mongo-express_1
````
- Ingresamos al aplicativo web con un navegador, el cual esta publico en el puerto 8080. Recuerden que si lo vamos a consultar desde nuestro equipo, debemos usar la IP 127.0.0.1 o localhost. Por ejemplo desde nuestro equipo:
````bash
http://<IP-Servidor-Docker>:3000
````
