# UC04: Administrar Sala de Juego - Diagrama de Actividades

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

' === DEFINICIÓN DE SWIMLANES (RAÍLES) ===
|#ddeeff|Usuario Organizador|
|#e6ffe6|Aplicación Mobile|
|#fffbe6|Backend Server|
|#ffe6e6|WebSocket Manager|

title "Diagrama de Actividades - UC04: Administrar Sala de Juego"

|Usuario Organizador|
start
:Selecciona "Crear Sala" desde juego VASTA;

|Aplicación Mobile|
:Valida que usuario esté autenticado;
:Envía solicitud de creación de sala;

|Backend Server|
:Genera código único de 6 dígitos;
:Crea instancia de sala en memoria;
:Asigna usuario como organizador;

|WebSocket Manager|
:Establece conexión WebSocket dedicada;
:Configura eventos de sala;

|Backend Server|
:Retorna datos de sala creada;
:Incluye código de acceso;

|Aplicación Mobile|
:Genera código QR automáticamente;
:Navega a pantalla de administración;
:Muestra código y QR code;

|Usuario Organizador|
:Configura parámetros del juego;
note right: Tiempo por turno: 5 seg\nNúmero de rondas: 10

|Aplicación Mobile|
:Valida configuración ingresada;
:Envía configuración al backend;

|Backend Server|
:Actualiza configuración de sala;
:Sincroniza cambios con todos los clientes;

|WebSocket Manager|
:Emite evento "configuracion-actualizada";

|Usuario Organizador|
:Comparte código QR con otros jugadores;

note right: Otros jugadores se van uniendo\na la sala usando el código

|WebSocket Manager|
:Recibe eventos "jugador-unido";
:Actualiza lista en tiempo real;

|Aplicación Mobile|
:Muestra jugadores que se van conectando;
:Actualiza contador de participantes;

|Usuario Organizador|
if (¿Hay mínimo 2 jugadores?) then (no)
  :Espera más jugadores;
  note right: Botón "Iniciar" deshabilitado
else (sí)
  :Botón "Iniciar Partida" se habilita;
  :Presiona "Iniciar Partida";
  
  |Aplicación Mobile|
  :Confirma inicio de juego;
  :Envía señal de inicio;
  
  |Backend Server|
  :Valida estado de sala;
  :Inicializa lógica del juego VASTA;
  :Crea estado inicial del juego;
  
  |WebSocket Manager|
  :Emite "juego-iniciado" a todos los clientes;
  :Sincroniza estado inicial;
  
  |Aplicación Mobile|
  :Cierra pantalla de administración;
  :Navega a pantalla de juego;
  :Carga interfaz de VASTA;
  
  |Usuario Organizador|
  :Comienza a jugar como participante;
  stop
endif

@enduml

```