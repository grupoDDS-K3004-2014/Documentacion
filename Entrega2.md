<h2>Entrega 2:</h2>

•	Cómo se incorpora cada funcionalidad pedida a lo desarrollado anteriormente

La solución con decorator solo agrega una superclase llamada Partido. La clase que anteriormente conocíamos como Partido tuvo que refactorearse a PartidoPosta. Esta, junto con PartidoDecorator,  se extiende de la superclase, la cual agrega las funcionalidades necesarias. La lógica de PartidoPosta no es alterada.
Por su parte, el observer implicó agregar la interfaz Observer, la cual es conocida por diferentes clases “observadoras” correspondientes a las diferentes funcionalidades (notificar a la lista de amigos y notificar al administrador por temas relacionados con los equipos completos). Partido es quien tiene una colección de observers, por lo tanto sus métodos fueron modificados para agregar estas llamadas a la nueva interfaz.

•	Qué consecuencias trae en cada solución el manejo de la identidad de los objetos existentes  

En la solución con observer no es necesario pensar en manejo de identidad ya que el comportamiento va a estar dado por la clase en sí (Partido) y además no hay objetos compartidos (solo el mock servidorDeEmails). Por otro lado, en la solución con decorator, si bien el patrón utilizado se presta para hablar de identidad ya que vas referenciando objetos a través de otros, en este caso no se utilizó ya que no hay objetos compartidos, ni necesitás compararlos.


•	Cómo ayuda cada solución a aumentar la cohesión de los componentes.

La solución con observer aumenta la cohesión solo en las consignas del dominio que implican notificaciones (ya que para esto usamos observers), mas no así en el resto de ellas, ya que simplemente hubo que modificar el comportamiento en las clases en las que lo creímos necesario.
En el decorator sí se vé claramente el aumento de la cohesión ya que el comportamiento no se ve modificado directamente en la clase sino que se relaciona a ésta con otros objetos que agregan o modifican comportamiento (PartidoPosta no fue editado para cambiar su comportamiento sino que PartidoDecorator se encarga de, por ejemplo, da de baja a un participante).


