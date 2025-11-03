# UC01: Administrar Perfil de Usuario - Diagrama de Actividades

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
|#ffe6e6|Firebase Services|

title "Diagrama de Actividades - UC01: Administrar Perfil de Usuario"

|Usuario|
start
:Abre la aplicación LastShot;

|Aplicación Mobile|
:Verifica estado de sesión;
if (¿Usuario autenticado?) then (no)
  :Muestra pantalla de login/registro;
  |Usuario|
  :Selecciona "Registrarse";
  :Ingresa email y contraseña;
  
  |Aplicación Mobile|
  :Valida formato de datos;
  :Envía datos de registro;
  
  |Backend Server|
  :Recibe solicitud de registro;
  :Valida datos del usuario;
  
  |Firebase Services|
  :Crea cuenta en Firebase Auth;
  :Genera UID único;
  :Retorna confirmación;
  
  |Backend Server|
  :Crea perfil en Firestore;
  :Genera token JWT;
  :Envía respuesta exitosa;
  
  |Aplicación Mobile|
  :Almacena token localmente;
  :Muestra mensaje "Registro exitoso";
else (sí)
  :Carga perfil del usuario;
endif

:Muestra pantalla principal del perfil;

|Usuario|
:Selecciona "Editar perfil";

|Aplicación Mobile|
:Muestra formulario de edición;

|Usuario|
:Modifica nombre y avatar;
:Confirma cambios;

|Aplicación Mobile|
:Valida nueva información;
:Envía actualización al backend;

|Backend Server|
:Procesa cambios del perfil;

|Firebase Services|
:Actualiza documento en Firestore;
:Confirma actualización;

|Backend Server|
:Retorna confirmación de cambios;

|Aplicación Mobile|
:Actualiza interfaz con nuevos datos;
:Muestra mensaje "Perfil actualizado";

|Usuario|
:Visualiza perfil actualizado;
stop

@enduml

```