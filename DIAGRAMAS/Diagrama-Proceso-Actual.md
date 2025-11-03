# Diagrama del Proceso Actual - Juegos Físicos

```plantuml
@startuml
|#lightblue|Organizador|
start
:Planifica evento social;
:Revisa materiales disponibles;
if (¿Tiene todos los materiales?) then (No)
  :Sale a comprar/conseguir materiales;
  :Regresa con materiales;
else (Sí)
endif
:Prepara espacio físico;
:Organiza mesas y sillas;

|#lightgreen|Participantes|
:Llegan al evento;
:Se sientan en círculo/mesa;

|#lightblue|Organizador|
:Explica reglas del juego;
:Distribuye materiales físicos;
:Configura tablero/cartas/dados;
:Da inicio al juego;

|#lightgreen|Participantes|
repeat
  :Esperan su turno;
  :Realizan jugada manual;
  if (¿Surgió disputa?) then (Sí)
    |#lightblue|Organizador|
    :Consulta manual de reglas;
    :Aclara situación;
    |#lightgreen|Participantes|
  else (No)
  endif
  :Continúan jugando;
repeat while (¿Juego terminado?) is (No)

|#lightblue|Organizador|
:Cuenta puntos manualmente;
:Verifica resultados;
:Declara ganador oficial;
:Anota resultados en papel;

if (¿Jugar otro juego?) then (Sí)
  :Recoge materiales anteriores;
  :Prepara nuevo juego;
else (No)
  :Guarda todos los materiales;
  :Limpia espacio;
endif

|#lightgreen|Participantes|
:Se despiden del evento;
stop
@enduml
```