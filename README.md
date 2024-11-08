# Config Server

Este proyecto es un Config Server creado con Java 23 y Spring Boot 3.3.5, diseñado para centralizar la configuración de tus microservicios.

## Requisitos
- Java 23
- Docker (para dockerizar y ejecutar en contenedores)

## Estructura del Proyecto
El Config Server está configurado para leer archivos .properties almacenados en el repositorio de configuración [ecommerce-dev-props](https://github.com/ecommerce-portafolio/ecommerce-dev-props).

## Ejecución Local
Para ejecutar el Config Server localmente:

```
./mvnw spring-boot:run
```
El Config Server estará disponible en http://localhost:8888.
Puedes cambiar este puerto en ``application.yml``

## Dockerización

### Construir la imagen Docker

Para dockerizar el Config Server, usa el siguiente comando:
```
docker build -t config-server .
```

### Ejecutar el contenedor Docker
Para ejecutar el Config Server en un contenedor Docker:
```
docker run -p 8888:8888 --name my-config-server config-server
```
Esto expondrá el Config Server en el puerto 8888 de tu máquina local.

## Acceso

Una vez iniciado el Config Server, puedes acceder a la configuración de un servicio específico con una URL en el siguiente formato:

```
http://localhost:8888/{application}/{profile}
```
- application: nombre de la aplicación que solicita la configuración.
- profile: perfil de configuración (como dev, prod, etc.).