# Arquitectura front-end

## info
@carlosvillu
youtube.com/carlosvillu

Creación de markeplacets, infojob, fotocasa, mil anuncios. Empresa de noruega.

## Experiencoia

- Nos cuenta su experiencia en relación al acomplamiento de una app con jQuery.
Código spaggeti, js file de 13k lineas.
- jQuery era la arquitectura... WTF?!!! Tienes en u solo fichero hilo de conocimiento.
- Esto obligaba a que el que toca el fichero... era el último que había tocado el fichero. Esto crea cuellos de botella
- Esto implica que cambiar lo que sea, hace que la aplicación explote.

### Conclusiones
- El negocio no puede parar
- El SEO es crítico
- Estás en fase de desarrollo en un refactor de backend.


##Propuesta de solución
- Business rules => los hilos de conocimiento no pueden estar dentro de los ficheros. Lo que crea la web no es la interfaz sino la lógica de negocio.
- Hay que darle un cuerpo, teniendo dos vertientes: SUI components - Site components -> tenemos que ser capaz de temar los componentes.

- Apilas capas como SUITheme, Site Theme, Web app. Pero se necesita un servicio que lo aglutine.
- Además se necesita que fluya el conocimiento de las capas interiores a las exteriores. Las reglas de negocio tienen que funcionar independientemente de que sea lo que pinte.
- La salida de todas estas capas debe ser una SPA. Esto es una declaración de intenciones. Esto va enfocado al client site rendering.
- *PERO SEGUIMOS NECESITANDO SSR* ya que google no es capaz aún de manejar el SEO fuera de el.

## Reglas de negocio

-¿El trozo de código se reiere a una validación, un calculo, una llamada a otro sistema? Si es un si, se corresponde a una regla de negocio y es necesario ubicarla donde corresponde. Para ello debemos utilizar la arquitectura hexagonal.

### Un lugar para cada cosa, y cada cosa en su lugar
Cuando usas una feature, sabes exactamente en que parte va tu código, o sabes exactamente que código hay que tocar.

- Es necesario dar semantica a nuestra aplicación.
- Existe el concepto de repositorios.
- Por ejemplo: cuando usas SSR, no puedes acceder a localstorage directamente, tendrás que tener un repository en backend.
- Hay que definir caos de uso. Si no te sientas con alguien de producto, ves que pasa y le das un nombre, es imposible. Esto añade semántica a la app.

## Tu lógica de negocio no tiene estado
- No puede tener estado
- Tiene que estar completamente desacoplado de la interfaz.

# Patrón de componentes y contenidos
- El contenedor sabe como interacturar con el negocio, pero no sabe generar contenido.
- El componente no sabe del negocio, pero si de generar contenido.

## SUI Theme
La comunicación con la gente de UX no es todo lo fluida que debería de ser.
El SUI Theme es un contrato. Se definen tamaños fijos, colores fijos. ¿Cual es el color primary? ¿Cual es el tamaño S, M o XL?

Cada capa debería ser un paquete aislado de NPM.

Por definición se debería desarrollar en componentes aislados. Se pueden instalar por separado.
Usar concepto de mono-repo, multi paquete.

## SSR Opensource y Opcional
Solo existe para el SEO
Mejora el rendimiento de una SPA, usando un SSR con hydration.

## Not just a theory
Es algo real.




