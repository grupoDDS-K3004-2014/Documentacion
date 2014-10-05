<h2>Entrega 6:</h2>

Partimos del hecho que la aplicación a desarrollar está pensada para organizar partidos de fútbol  5 con miembros de una comunidad formada por aproximadamente 25 personas. Esto implica que la densidad de datos con la que trabaja el programa no es muy grande, ni tampoco la variación de los mismos. Además, los casos de uso contemplados en la aplicación son de acceso únicamente para el administrador, por lo que la misma no será de uso masivo (distinto sería si cualquier jugador pudiera acceder para darse de baja, por ejemplo).

La decisión de trabajar con Arena se basó en la magnitud de la aplicación: es relativamente pequeña, maneja pocos datos y tiene un único usuario, como se detalló arriba. Arena justamente utiliza una arquitectura centralizada y permite obtener interfaces de escritorio. El primer punto implica que el modelo y la vista se encuentran en el mismo lugar (la computadora del administrador, en este caso) y se justifica por la falta de necesidad de almacenar un gran número de datos o variadas funcionalidades en un servidor externo. Por otro lado, se decidió que la aplicación sea de escritorio porque es lo más simple y directo de manejar para el administrador.