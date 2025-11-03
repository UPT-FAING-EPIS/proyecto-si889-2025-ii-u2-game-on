# UC02: Explorar Juegos Multijugador - Diagrama de Actividades

```plantuml
@startuml
' === CONFIGURACIÓN VISUAL ===
!theme plain

skinparam backgroundColor #ffffff
skinparam activity {
  BackgroundColor white
  BorderColor #666666
  FontColor #111111
  FontSize 17
}
skinparam titleFontColor #222222
skinparam titleFontSize 22
skinparam swimlaneFontColor #222222
skinparam swimlaneBorderColor #aaaaaa
skinparam swimlaneFontSize 18
skinparam arrowColor #444444
skinparam arrowThickness 2
skinparam defaultFontName Arial

' === DEFINICIÓN DE SWIMLANES ===
|#ddeeff|Usuario|
|#e6ffe6|Aplicación Mobile|
|#fffbe6|Backend Server|
|#ffe6e6|WebSocket Manager|

title "Diagrama de Actividades - UC02: Explorar Juegos Multijugador"

|Usuario|
start
:Accede a sección "Juegos Multijugador";

|Aplicación Mobile|
:Carga lista de juegos disponibles;
:Muestra opciones [VASTA, El Infiltrado];

|Usuario|
:Selecciona juego "VASTA";

|Aplicación Mobile|
:Muestra opciones: "Crear Sala" o "Unirse a Sala";

|Usuario|
:Selecciona "Unirse a Sala";
:Ingresa código de sala "ABC123";

|Aplicación Mobile|
:Valida formato del código;
:Establece conexión WebSocket;

|WebSocket Manager|
:Conecta con servidor backend;
:Escucha eventos de sala;

|Backend Server|
:Verifica existencia de sala "ABC123";
if (¿Sala existe?) then (no)
  :Retorna error "Sala no encontrada";
  |Aplicación Mobile|
  :Muestra mensaje de error;
  |Usuario|
  :Reintenta con nuevo código;
  stop
else (sí)
  if (¿Hay espacio disponible?) then (no)
    :Retorna error "Sala llena";
    |Aplicación Mobile|
    :Muestra mensaje "Sala completa";
    stop
  else (sí)
    :Añade usuario a la sala;
    :Actualiza lista de jugadores;
  endif
endif

|WebSocket Manager|
:Emite evento "jugador-unido";
:Sincroniza estado con todos los clientes;

|Aplicación Mobile|
:Recibe confirmación de unión;
:Navega a pantalla de lobby;
:Muestra jugadores conectados;

|Usuario|
:Visualiza lobby con otros jugadores;

note right: El usuario espera a que\nel organizador inicie la partida

|WebSocket Manager|
:Escucha evento "juego-iniciado";

if (¿Organizador inicia juego?) then (sí)
  |Backend Server|
  :Valida mínimo de jugadores;
  :Inicializa estado del juego;
  :Emite "juego-iniciado" a todos;
  
  |WebSocket Manager|
  :Recibe señal de inicio;
  
  |Aplicación Mobile|
  :Carga pantalla del juego VASTA;
  :Sincroniza estado inicial;
  
  |Usuario|
  :Comienza a jugar;
  stop
else (no)
  :Continúa esperando en lobby;
  stop
endif

@enduml

```