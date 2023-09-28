## 1 Crear partida
**Caso de uso número 1**: Crear partida.
**Actor primario:** Usuario.
**Actores secundarios:** Sistema. 
**Precondición:** Usuario ya registrado (dio su nombre de usuario).
#### Escenario exitoso principal: 
1) Jugador ingresa al menú de creación de partidas.
2) Sistema le da al usuario un formulario que debe ser completado con la configuración de partida, es decir: mínimo de jugadores (4 o más), máximo de jugadores (12 o menos), nombre y un campo opcional para la contraseña.
3) Jugador ingresa los datos requeridos por el formulario y confirma la creación de partida. 
4) Sistema proporciona un mensaje de confirmación, y lleva al usuario al menú de sala de espera. 
#### Escenario excepcional 1:
3) a) Jugador ingresa datos erróneos. 
	1) Sistema informa del problema y se vuelve al paso 2 del escenario exitoso principal.

## 2 Turno completo
**Caso de uso número 2**: Jugar turno completo.
**Actor primario:** Jugador.
**Actores secundarios:** Sistema y jugadores que no están en su turno. 
**Precondición:** El jugador esta en su turno
#### Escenario exitoso principal: 
1) El Jugador levanta una carta del mazo.
2) El Sistema le informa al jugador la carta ¡Aléjate! que levantó y le indica que seleccione una de sus 5 cartas.
3) El Jugador selecciona una carta.
4) El Sistema le presenta tres opciones al jugador
	- Cambiar su selección, lo que vuelve al paso 3).
	- Descartar la carta.
	- Jugar la carta.
5) El Jugador opta por jugar la carta.
6) El sistema interpreta los efectos de la carta y la descarta.
7) El sistema informa tanto al jugador en su turno como al jugador que sigue, que elijan cartas para intercambiar.
8) Ambos jugadores seleccionan sus cartas para intercambiar y confirman su selección.
9) El sistema verifica que no hay ninguna infección.
10) El sistema le da la carta de turno al siguiente jugador.
#### Escenario alternativo 1: 
2) a) El sistema le informa al jugador la carta ¡Pánico! y la juega.
	1) Se va al paso 6 del escenario exitoso principal.
#### Escenario alternativo 2:
5) a) El jugador opta por descartar la carta.
	1) El sistema descarta la carta. 
	2) Se va al paso 7 del escenario exitoso principal.
#### Escenario alternativo 3:
7) a) El sistema informa tanto al jugador en su turno como al jugador que sigue, que un efecto impide su intercambio de cartas. 
	1) Se va al paso 10 del escenario exitoso principal.
#### Escenario alternativo 4:
8) a) El jugador que no esta en su turno elige jugar una carta de defensa.
	1) El sistema interpreta el efecto de la carta jugada.
	2) Se va al paso 10 del escenario exitoso principal
#### Escenario alternativo 5:
9) a) El sistema reconoce que uno de los jugadores recibió una carta de infección del jugador con rol "La Cosa" y actualiza el rol del primero a "Infectado". 
	1) Se va al paso 10 del escenario exitoso principal.
#### Escenario alternativo 6: 
9) b) El sistema reconoce que uno de los jugadores está superinfectado y lo elimina de la partida. 
	1) Se va al paso 10 del escenario exitoso principal.
#### Escenario alternativo 7: 
7) a) El sistema reconoce que la carta jugada afecta a quién intercambia.
	1) El sistema informa al jugador que juega su turno que debe seleccionar un jugador vivo para intercambiar según las restricciones de la carta que jugó.
	2) El jugador selecciona con quien va a intercambiar.
	3) El sistema informa de la selección a todos los jugadores.
	4) El sistema informa tanto al jugador en su turno como al jugador seleccionado, que elijan cartas para intercambiar.
	5) Se va al paso 8 del escenario exitoso principal.
#### Escenario excepcional 1:
5) b) El jugador opta por descartar la carta y esta no se puede descartar por las reglas (es la carta de "La Cosa" o es una carta "Infectado" y el jugador no es la cosa ni está infectado). 
	1) Se va al paso 4 del escenario exitoso principal.

## 3 Jugar una carta sospecha
**Caso de uso número 3**: Jugar una carta sospecha.
**Actor primario:** Jugador.
**Actores secundarios:** Sistema, Otro jugador.
**Precondición:** El jugador levantó una carta del mazo y no es carta de ¡Pánico!. El jugador tiene en su mano la carta "Sospecha"
#### Escenario exitoso principal: 
1) El jugador elije jugar la carta sospecha. 
2) El sistema le da a elegir al jugador sobre qué otro jugador va a usar la carta.
3) El jugador elige otro jugador.
4) El sistema informa a todos los jugadores que se jugó el efecto de la carta de sospecha sobre ese otro jugador.
5) El sistema le da a elegir cuál de las cartas del otro jugador va a ver.
6) El jugador elige la carta que quiere ver. 
7) El sistema le muestra la carta al jugador. Y le informa al otro jugador qué carta le vieron. 
#### Escenario alternativo 1:
4) a) El sistema detecta que el jugador elegido es adyacente al jugador y además hay un efecto de "Puerta atrancada" entre ellos. Y el sistema informa al jugador de esto.
	1) Se vuelve al paso 2 del escenario exitoso principal