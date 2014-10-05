<h2>Entrega 4:</h2>

Para el ordenamiento de los jugadores, de utiliza una interfaz Criterio que establece polimórficamente los criterios (handicap, promedio de calificaciones último partido, promedio calificaciones de los últimos n partidos y criterios compuestos, por el momento) que generaran una lista que decidimos llamar "puntajesCriterio", cuyos elementos los utilizará el sistema para ordenar a los participantes.

El hecho de que los criterios se puedan agregar como parte de una interfaz nos otorga la posibilidad de poder agregar más criterios a futuro: lo único que deben respetar estos es que generen un elemento en la lista puntajesCriterio. Esto implica cohesión y flexibilidad.

Para encarar los criterios compuestos utilizamos el patrón Composite que se vale del método determinarPuntajeCriterio() de los demás criterios para obtener el suyo.

Se implementa una clase para los algoritmos de division de equipos. Esta solucion permite delegar la responsabilidad del armado de equipos, aumenta la cohesion y la flexibilidad al existir la posibilidad de agregar otros algoritmos de division a futuro.

Se implementa un Command para separar el momento de generacion de equipos tentativos, del momento de confirmar equipos, lo cual aporta flexibilidad pues permite generar tantos equipos tentativos como se desee antes de confirmar los que jugaran.
