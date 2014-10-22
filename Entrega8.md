Documentacion
=============

[Diagrama de Entidad Relación](http://i.imgur.com/1WKKxRX.png)

En respuesta a los requerimientos solicitados en el punto 3 de la entrega 8 del TP:
a.	Saber los jugadores malos, con un hándicap de 5 ó menos.

Esto se logra consultando el campo *handicap* de la tabla *Participantes*:
1.	**Select** sobre la tabla Participantes de aquellos cuyo handicap sea menor a 5.
2.	Project de la tabla obtenida en (1) de los campos idParticipante, nombre y apellido.


b.	Saber qué jugadores son traicioneros, los que tuvieron más de 3 infracciones el último mes.

Se logra trabajando con las tablas Participantes e Infracciones:
1.	Select sobre la tabla Infracciones filtrando las fechas posteriores a 30 días atrás.
2.	Join entre tabla (1) y Participantes respecto al campo idParticipante.
3.	Project de la tabla obtenida en (2) de los campos idParticipante, nombre y apellido.


c.	Saber cuántos jugadores podrían “mejorar” con el tiempo, son los jugadores malos que tienen menos de 25 años (nota: debe evitar lógica duplicada).

Se opera con la tabla Participantes:
1.	Se repiten los pasos del punto a.
2.	Select sobre la tabla Participantes comparando que fechaNacimiento sea mayor a 25 años atrás.
3.	Project sobre la tabla (2) sobre idParticipante.
4.	Join entre las tablas obtenidas en (1) y (3) respecto a idParticipante.


d.	Reflejar que un jugador se da de baja a un partido.

Se obtiene de las tablas Inscripciones y Participantes:
1.	Select de la tabla Inscripciones respecto a estado = ‘baja’
2.	Project de (1) sobre idParticipante.
3.	Join entre (2) y Participantes respecto a idParticipante.
4.	Project de la tabla obtenida en (3) de los campos idParticipante, nombre y apellido.


e.	Cada vez que un jugador se baje de un partido se le debe agregar una infracción si no ofrece reemplazante.

Este punto se consigue con un trigger, que cada vez que se hace un update sobre Inscripción, crea una infracción en la tabla Infracciones que estará a nombre del participante que se dio de baja.
