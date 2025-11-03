# UC02: Explorar Juegos Multijugador - Diagrama de Secuencia

```plantuml
@startuml
!theme plain
title "Diagrama de Secuencia - UC02: Explorar Juegos Multijugador\n(Boundary - Control - Entity - Actor)"

' === ACTORES ===
actor "👤 Usuario Jugador" as Usuario

' === BOUNDARY ===
participant "🖥️ MultiplayerScreen\n<<Boundary>>" as Boundary1 #LightSkyBlue
participant "🎮 GameLobby\n<<Boundary>>" as Boundary2 #LightSkyBlue

' === CONTROL ===
participant "🔌 SocketService\n<<Control>>" as Control1 #LightGreen
participant "🖥️ Backend Server\n<<Control>>" as Control2 #LightGreen
participant "⚙️ VastaGame Handler\n<<Control>>" as Control3 #LightGreen

' === ENTITY / DATABASE ===
database "💾 Game Rooms\n<<Database>>" as Entity1 #LightCoral

' ====================================================
== Explorar y Seleccionar Juego ==

Usuario -> Boundary1: accederJuegosMultijugador()
Boundary1 -> Boundary1: cargarJuegosDisponibles()
Boundary1 -> Usuario: mostrarOpciones([VASTA, Infiltrado])

Usuario -> Boundary1: seleccionarJuego("VASTA")
Boundary1 -> Usuario: mostrarOpciones("Crear Sala", "Unirse")

' ====================================================
== Unirse a Sala Existente ==

Usuario -> Boundary1: seleccionarUnirse()
Usuario -> Boundary1: ingresarCodigo("ABC123")
Boundary1 -> Boundary1: validarFormatoCodigo("ABC123")

Boundary1 -> Control1: conectarWebSocket()
Control1 -> Control2: establecerConexion()
Control2 -> Control1: conexionEstablecida()
Control1 -> Boundary1: conexionConfirmada()

Boundary1 -> Control1: unirseASala("ABC123", userData)
Control1 -> Control2: emit("join-room", {codigo, usuario})

Control2 -> Entity1: verificarSala("ABC123")
alt Sala existe y tiene espacio
    Entity1 -> Control2: salaEncontrada()
    Control2 -> Entity1: añadirJugadorASala(usuario, "ABC123")
    Entity1 -> Control2: jugadorAñadido()
    Control2 -> Control1: emit("jugador-unido", salaData)
    Control2 -> Control1: emit("sala-actualizada", jugadoresList)
    
    Control1 -> Boundary1: recibirEventoUnion(salaData)
    Boundary1 -> Boundary2: navegarALobby(salaData)
    Boundary2 -> Usuario: mostrarLobby(jugadores)
    
    ' ====================================================
    == Sincronización en Tiempo Real ==
    
    loop Esperando más jugadores
        Control2 -> Control1: emit("jugador-nuevo", nuevoJugador)
        Control1 -> Boundary2: actualizarListaJugadores()
        Boundary2 -> Usuario: mostrarNuevoJugador()
    end
    
    ' ====================================================
    == Inicio del Juego ==
    
    note over Usuario: Organizador inicia el juego
    
    Control2 -> Control3: iniciarJuego("ABC123", "VASTA")
    Control3 -> Entity1: validarMinJugadores()
    Entity1 -> Control3: validacionCompleta()
    Control3 -> Control3: inicializarEstadoJuego()
    
    Control3 -> Control2: juegoInicializado(estadoInicial)
    Control2 -> Control1: emit("juego-iniciado", estadoInicial)
    
    Control1 -> Boundary2: recibirInicioJuego(estadoInicial)
    Boundary2 -> Boundary1: navegarAJuego("VASTA", estadoInicial)
    Boundary1 -> Usuario: mostrarPantallaJuego()

else Sala no existe o está llena
    Entity1 -> Control2: salaNoDisponible()
    Control2 -> Control1: emit("error-union", mensaje)
    Control1 -> Boundary1: mostrarError(mensaje)
    Boundary1 -> Usuario: mostrarMensajeError()
end

@enduml
```