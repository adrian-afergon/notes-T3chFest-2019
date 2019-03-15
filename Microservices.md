# Microservicios: gRPC vs REST

## Contacto
Stephan Dorado

## GRPC
framwrok para microservicios creado por Google
Da solución al como extructurar nuestro microservicio de forma ordenada, escalable.

- Se basa en HTTP/2, no como Rest que se basa en HTTP/1.
- Define como se comunican nuestros microservicios.

- Gasta pocos recursos ya que no tiene que abrir y cerrar comunicaciones constantemente.

## HTTP/2 & protocolbuf
HTTP/1 -> 1999
HTTP/2 -> 2015

HTTP/2
- multiplexed. Multi response/request. Es similar a los webSockets en HTTP/1

El protocol buffer es tipado.

- Un simple cambio implica tener que recompilar toda la aplicación.

## Securizar el servicio

Con gRPC no tienes que securizar, ya que va por HTTP/2.

En el código solo tenemos que definir donde está en certificado del servidor, y pasarle las credenciales necesarias.

## Error Handling

Se simplifica a 17 tipos de errores. Del 0 al 16.
- Cada error está cerrado a un caso concreto.
- La gestion de errores es complicada

## Load Balancing

- Balancing -aware client
- Proxy load balancing
- Look-asside load balancing service

## Interceptores

- Se puede tener a nivel de cliente o a nivel de servidor.
- Los interceptores funcionan en pilas


