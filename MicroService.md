#Micronaut

micronaut -> spring boot -> microservicios

java, groovie, kotlin

ultra ligero, reactive, netty

ahead of time compilation (AOT)

--------------------------------------------------------

se genera ¡n las anotaciones en tiempo de compilación y no tiene que sintentizar nada
no usa dinamic class loading, no se necesita reflexión, evita AOT

Natively cloud native

arranque rápido

https://micronaut.io/

similar a AWS lambda. Sel levanta en cada llamada, con lo cual interesa que sea rápido.

Las aplicaciones son fáciles de testear.

encaha bien con GraalVM. usa binarios nativos de la plataforma.

----------------------------------------------------------------------------

Tiene un CLI, es opcional.

sdk manager install (java, ruby, kotlin, gradle)

profiles preconfigurados

skills de alexa que se despliegan directamente en lamba

por defecto va a crear java

-----------------------------------------------------------------------------

EL REPO.

-----------------------------------------------------

usa spok y @MicronautTest

usar reactive para crear código non blocking, vale cualquiera. (just)

Comenta usar 2e2 en relaidad de usar test unitarios porque no tienes problemas de velocidad

anotaciones standar.

-------------------------------------------------------

service discovery, como se encuentran los microservicios? añadir deopendencia de consult y su configuración.

exponer gateway a los clientes

balanceos, fallbacks, etc

----------------------------------------------------------

El pojo y cliente que se comparte, se debería crear un multiproyecto jar para que ambos lean la misma interfaz y firma.

----------------------------------------------------------

Definir que eres un cliente del servicio con el nombre que has definido en consult

por defecto ya tiene round robin.

##Cuando tenemos microservicios debemos preveer que la app va a fallar, debemos definir fallbacks
¿como se hace en el http?

anotarla como fallback y devolver un valor por defecto - vacio. Tolerancia a errores.

se pueden definir retriable para que haga reintentos. Solo devolverá el fallback cuando se cumpla


Hipstricks. -> Circuit breacker

--------------------------------------------------------------

Distributing tracing permite tener la trazabilidad en un único sitio de los logs de todos los microservicios.

añadir configuración de zipking - se pueden samplear.
Te pinta la nube de microservicios y dependencias.

----------------------------------------------------------------

para utilizar graalvm, es necesario cambiar a la jvm de graal.

no soportado en windows

Es igual que spring, pero intentando funcionar internamente de otra manera para mejorar.

github.com/micronaut-projects/micronaut-core
guides.micronaut.io
gitter.im/micronautfw

@ilopmar

lopez.ivan@gmail.com


bit.ly/t3chfest-micronaut

