Entrega 7
===================


Muestre un ejemplo de cómo resolvió en el TP cada uno de los siguientes temas:
  1. Layout ⇒  disposición visual de controles
    * [Vamos a tomar como ejemplo la ventana de organización de equipos, ya que es la más compleja] (http://imgur.com/a/86p5w)


  2. Separación entre modelo y vista ⇒ grado de acoplamiento entre ambos concerns
    * A la hora de realizar la vista, logramos hacer que el dominio no esté acoplado a la vista, ya que en este solo estan las reglas de negocio (ordenar equipos, separarlos, inscribir jugador) y nada relacionado con cosas necesarias para la vista. Lo que se necesitó agregar para la UI, fué incluido en los distintos application models que utilizamos (por ejemplo en la AM del organizador de equipos se incluyó un atributo que servia como criterio compuesto de ordenamiento, así podíamos meter todos los criterios que marcaba el usuario, sin agregar comportamiento al partido). 
    * El único punto flojo fue que agregamos un atributo de confirmación al partido, ya que necesitabamos saber si el partido estaba confirmado, y no se nos ocurrió ninguna otra forma. También fué necesario agregar la annotation @Observable e implementar Entity en las clases que se iban a mostrar en pantalla. Sin embargo, tranquilamente se podría cambiar la vista por otra, ya que están ubicados en dos proyectos distintos (mostrando aún más la independencia del dominio hacia la vista).
    * Resumen: Vista acoplada con el dominio (ya que está totalmente basada en el), pero el dominio está desacoplado de la vista (estas podrian ser intercambiables)
  
  

  3. Manejo del estado conversacional de los datos que se cargan en la vista
    * Cada ventana necesita distintos juegos de datos (su respectivo application model o en el caso de la ventana para inspecionar jugadores a este en cuestión), aunque había algunos que se repetian (los jugadores, los partidos). Decidimos persistir los jugadores y los partidos (datos puros del dominio) a dos homes (homeJugadores y homePartidos), para que los application models puedan conseguir (si necesitan) a estos. Hubo que primero instanciar jugadores y luego partidos, para poder subscribirlos.
    * La ventana para generar equipos trabaja todo sobre un clon del partido, así si el usuario pone cancelar, no se produce ningún cambio (al usar bindings me modificaria el partido todo el tiempo, haciendo imposible volver atrás)


|  Ventana principal | Ventana de busqueda | Ventana de organización | Ventana de jugador|
|:------------------:|:-------------------:|:-----------------------:|:-----------------:|
| Partidos via home, instancia su applicationModel al crearse|Jugadores via Home, instancia su applicationModel al crearse |   Recibe el partido seleccionado al crearse|Recibe el jugador seleccionado al crearse |                   




  4. Binding unidireccional o bidireccional, comenten con cuál de los dos trabajaron y por qué.
    * Utilizamos bindings bidireccionales, ya que son los brindados con Arena, pero tranquilamente podríamos utilizar unidireccionales, ya que no tenemos bindeado nada que necesite estar actualizado en tiempo real sin necesidad de tocar un boton que haga algo (columnas de las tablas). Lo que necesitamos restringir como unidireccional (Nombre del partido, atributos del jugador, infracciones, etc) lo hicimos mostrandolo como un label con texto plano, así no se edita nada
  
  
  5. Manejo de eventos
    * La mayoría de los eventos son disparados con el click en un boton (confirmar partido, generar equipos, inspeccionar jugador, aceptar, cancelar, etc). Esto también incluye a las UserExceptions, ya que la lógica detras de los botones está dividida en dos partes: La validación de las precondiciones para efectuar la acción y la acción en cuestión. 
  

  6. Navegación
    * La UI parte desde una pantalla de "inicio" o ventana principal, en donde uno puede confirmar equipos, generar equipos o buscar jugadores. Generar equipos y buscar jugadores se abren en dialogs, los cuales a su vez pueden invocar otro dialog, la ventana de inspeccionar jugador.


  7. ¿Cómo es el flujo de una vista a otra?
    * Se puede bajar en el "arbol" de ventanas mediante botones, pero para subir es necesario aceptar, cancelar o tocar la cruz en los dialogos que se abran

* Ventana principal
  * Organizar Equipos
    * Inspeccionar jugadores  
  * Buscar jugadores
    * Inspeccionar jugadores    
  

 
  8. ¿Cómo se pasa información de una vista a otra?
    * Esta se para de 2 modos: Mediante el constructor de la nueva vista (como inspeccionar jugador y generar equipo), o se consigue pidiendosela a la home correspondiente (buscar jugador no recibe los jugadores en el constructor, sino que tiene especificado en su método de inicialización pedirle todos los jugadores a la home de jugadores)


