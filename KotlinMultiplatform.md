# Kotlin Multiplatform: un lenguaje para dominarlos a todos

## Contacto
Sergio casero
Daniel Llanos
Desarrolladores de Android en WordLine

## Kotlin Multiplataforma
Applicación -> Votlin

## Clean Architecture
- Los modelos de dominio van a ser los mismos para todas las plataformas.

- Los casos de uso interactuan con los modelos de dominio (Son un poco pasabolas)

- Por encima se utiliza MVP (Model View Presenter). Esta lógica de presentación es común a todas las plataformas.

- Se utilzia el patrón Repository. Orquesta toda la lógica de datos. (Local y remoto).

- A nivel de vistas existen los Error Handler y los Executor (En el caso de Android el hilo de UI siempre tiene que existir, y es la forma de decirle quien es el hilo principal).

- Los ViewModel y los Activity no deben tener lógica de negocio.

*NOTA:* Para salir de esta arquitectura común, para cada plataforma en específico, es haciendo uso de interfaces.

*NOTA:* LAs co-rutinas, son funciones asíncronas que se ejecutan como si fuesen síncronas.

# Qué utilizar en cada capa
- Backend -> Ktor
- Android client -> Kotlin, accediendo al módulo de common.
- React -> Componente para enrutar -> Dicen que el código es muy malo, que les echen una mano con una PR ;-)
- IOs client -> Se aceptan también PR. para montar la navegación.

## Platform compilation
- Compilar para cada una de las plataformas. Es necesario compilar primero la parte de core para que esté disponible el dominio para todas las plataformas.

## ¿Como implementar una nueva plataforma?
Por ejemplo para implementar una plataforma deskto, solo sería necesario implementar la interfaz.
