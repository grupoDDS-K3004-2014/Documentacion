Entrega 7
===================


Muestre un ejemplo de cómo resolvió en el TP cada uno de los siguientes temas:
  1. Layout ⇒  disposición visual de controles
    * [Vamos a tomar como ejemplo la ventana de organización de equipos, ya que es la más compleja] (http://imgur.com/a/86p5w)


  2. Separación entre modelo y vista ⇒ grado de acoplamiento entre ambos concerns
    * A la hora de realizar la vista, logramos hacer que el dominio no esté acoplado a la vista, ya que en este solo estan las reglas de negocio (ordenar equipos, separarlos, inscribir jugador) y nada relacionado con cosas necesarias para la vista. Lo que se necesitó agregar para la UI, fué incluido en los distintos application models que utilizamos (por ejemplo en la AM del organizador de equipos se incluyó un atributo que servia como criterio compuesto de ordenamiento, así podíamos meter todos los criterios que marcaba el usuario, sin agregar comportamiento al partido). 
    * El único punto flojo fue que agregamos un atributo de confirmación al partido, ya que necesitabamos saber si el partido estaba confirmado, y no se nos ocurrió ninguna otra forma.    Sin embargo, tranquilamente se podría cambiar la vista por otra, ya que están ubicados en dos proyectos distintos (mostrando aún más la independencia del dominio hacia la vista).
    * Resumen: Vista acoplada con el dominio (ya que está totalmente basada en el), pero el dominio está desacoplado de la vista (estas podrian ser intercambiables)
  
  

  3. Manejo del estado conversacional de los datos que se cargan en la vista
    * Cada ventana necesita distintos juegos de datos (su respectivo application model o en el caso de la ventana para inspecionar jugadores a este en cuestión), aunque había algunos que se repetian (los jugadores, los partidos). Decidimos persistir los jugadores y los partidos (datos puros del dominio) a dos homes (homeJugadores y homePartidos), para que los application models puedan conseguir (si necesitan) a estos. Hubo que primero instanciar jugadores y luego partidos, para poder subscribirlos.


|  Ventana principal | Ventana de busqueda | Ventana de organización | Ventana de jugador|
|:------------------:|:-------------------:|:-----------------------:|:-----------------:|
| Partidos via home, instancia su applicationModel al crearse|Jugadores via Home, instancia su applicationModel al crearse |   Recibe al partido seleccionado al crearse|Recibe al jugador al crearse |                   




  4. Binding unidireccional o bidireccional, comenten con cuál de los dos trabajaron y por qué.
  
  
  5. Manejo de eventos
  

  6. Navegación
   
  
  7. ¿Cómo es el flujo de una vista a otra?
  
  
  8. ¿Cómo se pasa información de una vista a otra?


