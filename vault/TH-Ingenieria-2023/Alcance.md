El sistema de software requerido tiene como objetivo implementar del juego de mesa "La Cosa" con [estas reglas](https://famaf.aulavirtual.unc.edu.ar/pluginfile.php/27371/mod_resource/content/1/Reglas%20del%20Juego_%20La%20Cosa.pdf) de forma que se pueda jugar desde un navegador web. Como lo dicen las reglas, el juego es multijugador, es por esto que la implementación debe tener funcionalidades que faciliten la creación de partidas, la comunicación entre jugadores entre otras cosas.

Las partidas son creadas por jugadores, en el proceso de creación se asigna por partida un nombre para ésta, mínimo y máximo de jugadores siempre respetando el rango dado por las reglas (4-12) y finalmente una contraseña opcional. El jugador que crea la la partida pasa a ser su host. 

Cada partida puede estar en dos estados distintos, en sala de espera, o en juego. Durante ambos estados, cada partida cuenta con un chat en el que pueden participar todos los jugadores conectados. El jugador host es quien puede iniciar la partida una vez el mínimo de jugadores se unió. 

Los jugadores se pueden unir a una partida desde una lista con todas las partidas disponibles y dando la contraseña si es necesario. Una partida esta disponible para unirse si no se llego al máximo de jugadores y ademas no esta en juego. Los jugadores pueden salir de una partida solo cuando esta se encuentra en la sala de espera. Si el host de la partida se va, la partida se elimina.

Cuando una partida pasa a estar en juego, ningún jugador puede salir de la partida, ni finalizarla a la fuerza. Cuando un juego en la partida termina, esta vuelve al estado de sala de espera. Una partida no tiene limite respecto a la cantidad de juegos que se pueden jugar en ella. Una partida no puede tener dos o mas juegos simultáneamente. 

El sistema requerido, ademas de cumplir con las funcionalidades mencionadas, debe ser seguro y justo. Para asegurar que no se pueda acceder a datos de los jugadores desde su interfaz y para asegurar que los jugadores no puedan hacer trampa. Al ser un juego en linea multijugador, debe también ajustarse a los estándares de tiempos de respuesta. 

El sistema requerido no tendrá sistema de perfiles de usuario, amigos, ranking o puntaje. Tampoco tendrá partidas guardadas o partidas asincrónicas ni customización de las interfaces.   