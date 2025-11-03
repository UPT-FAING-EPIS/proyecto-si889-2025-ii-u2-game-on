# Diagrama del Proceso Propuesto - Aplicación LastShot

```plantuml
@startuml
|#lightblue|Usuario Organizador|
start
:Planifica evento social;
:Abre aplicación LastShot;
:Inicia sesión en la app;

|#orange|Sistema LastShot|
:Autentica credenciales;
:Carga perfil de usuario;
:Muestra pantalla principal;

|#lightblue|Usuario Organizador|
:Selecciona "Crear Juego";
if (¿Juego multijugador?) then (Sí)
  :Elige juego multijugador;
  :Configura parámetros;
else (No)
  :Elige juego solo device;
endif

|#orange|Sistema LastShot|
if (¿Es multijugador?) then (Sí)
  :Genera código único de sala;
  :Crea sala de espera;
else (No)
  :Prepara juego local;
endif

|#lightblue|Usuario Organizador|
if (¿Es multijugador?) then (Sí)
  :Comparte código de sala;
  
  |#lightgreen|Usuarios Participantes|
  :Abren aplicación LastShot;
  :Ingresan código de sala;
  
  |#orange|Sistema LastShot|
  :Valida código de sala;
  :Añade jugadores a la sala;
  :Sincroniza lista de participantes;
  
  |#lightblue|Usuario Organizador|
  :Ve lista completa de jugadores;
  :Presiona "Iniciar Juego";
else (No)
endif

|#orange|Sistema LastShot|
:Asigna turnos/roles aleatoriamente;
:Configura estado inicial del juego;
:Sincroniza con todos los dispositivos;

repeat
  |#lightgreen|Usuarios Participantes|
  :Esperan su turno;
  :Ven interfaz actualizada;
  if (¿Es su turno?) then (Sí)
    :Realizan acción en pantalla;
  else (No)
  endif
  
  |#orange|Sistema LastShot|
  :Recibe acción del jugador;
  :Valida reglas automáticamente;
  if (¿Acción válida?) then (No)
    :Envía notificación de error;
  else (Sí)
    :Actualiza estado del juego;
    :Sincroniza con todos los dispositivos;
  endif
  
  if (¿Juego terminado?) then (No)
    :Avanza al siguiente turno;
  endif
repeat while (¿Juego terminado?) is (No)

|#orange|Sistema LastShot|
:Calcula ganador automáticamente;
:Genera estadísticas del juego;
:Actualiza rankings de usuarios;

|#lightblue|Usuario Organizador|
|#lightgreen|Usuarios Participantes|
:Ven resultados en pantalla;
:Revisan estadísticas del juego;

|#lightblue|Usuario Organizador|
if (¿Jugar otro juego?) then (Sí)
  :Selecciona nuevo juego;
else (No)
  :Cierra sala de juego;
  
  |#orange|Sistema LastShot|
  :Libera recursos de la sala;
  :Guarda estadísticas;
  
  |#lightgreen|Usuarios Participantes|
  :Salen de la aplicación;
endif

stop
@enduml
```