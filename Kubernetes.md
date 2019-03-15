# Testeando Kubernetes: Escalabilidad y tolerancia a fallos

## Contacto
Micael Gallego
twitter: @micael_gallego
github: @micaelgallego

## Docker
Es casi un standar a la hora de crear contenedores y empaquetar aplicaciones.

Cuando nos enfrentamos a clusterizar, necesitamos un orquestador de conenedores
- Que nos ayude a desplegar
- Que nos ayude a actualizar
- Que se encargue de reiniciar servicios
- Que la plataforma nos ayude con la escalabilidad
- Que nos ayude a monitorizar

## Kubernetes
¿Cómo podemos gestionar la escalabilidad?

- Se empiezan creando recursos de tipo deployment que acaban creando pods
- La escalabilidad se consigue replicando los pods (replicas).
- Las peticiones se acaban repartiendo entre cada una de las réplicas
- Cada pod puede ejecutarse en cualquier nodo del cluster y pueden ser añadidos bajo demanda.

## Horizontal Pod Autoscaler
- En base a la carga que tiene el pod, interesa que replique automáticamente.
- Para coordinarte con el cloud en la nube -> Cluster autoscaling. Cuando ya no queden más post, se le solicita al proveedor.
- Vertical Pod autoscaler -> Cuando un pod consume mucho, se aumentan los recursos, pero implica que se tenga que reiniciar. Para ello se requiere que la aplicación se oueda reiniciar.

*NOTA:* Sobreescalar un poco si se desea anticipar a los picos. Ej: Por las noches hay más usuarios en Netflix.

- Si la aplicación es statefull -> Cuando un pod detecta que es stateless se cree que es el mismo usuario.
Podemos convertir estas apps statefull en stateless -> se puede hacer que la memoria en lugar de estar en el pod, esté en un lugar común disponible para todos los pots. (Sprint session). (Redis, MongoDb, MySql).

## Como hacer una BBDD escalable
- mysql-operator -> Aún están un poco verdes.
- Habla con tu proveedor, va a funcionar mucho más. Si no tienes conocimientos, mejor no hacerlo.

## Logs
- Los logs de los pops se tienen que poder gestionar y tener externalizados.
- Gestionar la comunicación entre servicios.
- Prometheos + Graphana
- ELK -> EFK (ElastickSearch FluentD Kibana)
- Zipkin

## Tenemos que adaptar las aplicaciones
Como desarrollador nada, como gestor del cluster si.

## Testing
- No debemos de basarnos solo en que nos conteste, sino la funcionalidad y el rendimiento.
- El directorio de estado para aplicaciones statefull, debe ser también escalable (Hazelcast).
- Herramientas: jmeter, loadmill, gatling...

### Observabilidad
Para testing automáticos necesitamos APIs en los test
- ElasticSearch
- Prometheos
- Kubernetes
- Zipkin

## Tolerancia a fallos
- Esto implica ser redundantes, Ej: tener master en zonas de disponibilida distitnas, lo mismo con los workers.

- ¿Como podemos probarlos? -> Chaos testing -> provoca fallos en ambitos limitados y de manera continua (Putea a la aplicación, mirndo lo que pasa).

- Chaos Monkey -> Simian Army.
- Gremlin -> Chaos as a Service
- Pod-Chaos-Monekys -> Script de bash
- Kube-Monkey
- Istio

## Istio
Herramienta que se configura por encima de Kubernetes, Inyecta un proxy al lado de cada servicio, en la entrada y salida de tu proxy.

Puede inyectar errores

http://elastest.io

