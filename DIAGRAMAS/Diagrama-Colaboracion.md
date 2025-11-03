# Diagrama de Colaboración - Sistema LastShot

```plantuml
@startuml
title Diagrama de Colaboración - Sistema LastShot

' ==== Objetos ====
object "Usuario" as Usuario
object "ProfileScreen" as ProfileScreen
object "AuthService" as AuthService
object "ApiService" as ApiService
object "BackendServer" as BackendServer
object "SocketService" as SocketService
object "GameLobby" as GameLobby
object "FirebaseFirestore" as FirebaseFirestore

' ==== Interacciones ====
Usuario --> ProfileScreen : abrirPerfil()
ProfileScreen --> AuthService : verificarSesion()
AuthService --> ProfileScreen : sesionActiva()
ProfileScreen --> Usuario : mostrarDatos()
Usuario --> ProfileScreen : editarPerfil(datos)
ProfileScreen --> AuthService : validarCambios()
AuthService --> ApiService : actualizarPerfil()
ApiService --> BackendServer : PUT /users/profile
BackendServer --> FirebaseFirestore : updateDocument()
FirebaseFirestore --> BackendServer : confirmacion()
BackendServer --> ApiService : respuestaExitosa()
ApiService --> AuthService : perfilActualizado()
AuthService --> ProfileScreen : datosGuardados()
ProfileScreen --> Usuario : mostrarConfirmacion()

Usuario --> GameLobby : unirseASala(codigo)
GameLobby --> SocketService : conectarWebSocket()
SocketService --> BackendServer : emit("join-room")
BackendServer --> SocketService : emit("jugador-unido")
SocketService --> GameLobby : actualizarLista()
GameLobby --> Usuario : mostrarJugadores()

@enduml

```