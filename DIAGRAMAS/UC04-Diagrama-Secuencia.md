# UC04: Administrar Sala de Juego - Diagrama de Secuencia

```plantuml
@startuml
!theme plain
title "Diagrama de Secuencia - UC04: Administrar Sala de Juego\n(Boundary - Control - Entity - Actor)"

' === ACTORES ===
actor "👑 Usuario Organizador" as Organizador

' === BOUNDARY ===
participant "🖥️ AdminScreen\n<<Boundary>>" as Boundary #LightSkyBlue

' === CONTROL ===
participant "🔌 SocketService\n<<Control>>" as Control1 #LightGreen
participant "📱 QRGenerator\n<<Control>>" as Control2 #LightGreen
participant "🖥️ Backend Server\n<<Control>>" as Control3 #LightGreen
participant "⚙️ SalaManager\n<<Control>>" as Control4 #LightGreen
participant "🎮 VastaGame\n<<Control>>" as Control5 #LightGreen

' === ENTITY / DATABASE ===
database "💾 Game Rooms\n<<Database>>" as Entity1 #LightCoral

' ====================================================
== Creación de Sala ==

Organizador -> Boundary: seleccionarCrearSala("VASTA")
Boundary -> Control1: conectarWebSocket()
Control1 -> Control3: establecerConexion()
Control3 -> Control1: conexionConfirmada()

Boundary -> Control3: crearSala("VASTA", organizadorData)
Control3 -> Control4: generarCodigoUnico()
Control4 -> Control3: codigo("ABC123")

Control3 -> Control4: crearInstanciaSala(codigo, organizador)
Control4 -> Entity1: inicializarSala(configuracionDefault)
Entity1 -> Control4: salaCreada()
Control4 -> Control3: salaCreada(salaData)

Control3 -> Control1: emit("sala-creada", salaData)
Control1 -> Boundary: recibirSalaCreada(salaData)

Boundary -> Control2: generarQRCode("https://lastshot.app/join/ABC123")
Control2 -> Boundary: imagenQR()
Boundary -> Organizador: mostrarAdminPanel(codigo, qrImage)

' ====================================================
== Configuración del Juego ==

Organizador -> Boundary: modificarConfiguracion(tiempoPorTurno: 5, rondas: 10)
Boundary -> Boundary: validarConfiguracion()
Boundary -> Control1: actualizarConfiguracion(nuevaConfig)
Control1 -> Control3: emit("actualizar-config", nuevaConfig)

Control3 -> Control4: aplicarConfiguracion(salaId, nuevaConfig)
Control4 -> Entity1: actualizarConfiguracion(nuevaConfig)
Entity1 -> Control4: configuracionActualizada()
Control4 -> Control3: configuracionActualizada()
Control3 -> Control1: emit("config-actualizada", nuevaConfig)

Control1 -> Boundary: recibirConfigActualizada()
Boundary -> Organizador: mostrarConfigConfirmada()

' ====================================================
== Gestión de Jugadores ==

loop Jugadores uniéndose
    note over Control3: Otros usuarios se unen usando el código
    
    Control3 -> Control1: emit("jugador-unido", nuevoJugador)
    Control1 -> Boundary: recibirNuevoJugador(jugadorData)
    Boundary -> Boundary: actualizarListaJugadores()
    Boundary -> Organizador: mostrarNuevoJugador()
    
    Boundary -> Boundary: validarMinimosJugadores()
    alt Mínimo 2 jugadores
        Boundary -> Boundary: habilitarBotonIniciar()
    end
end

' ====================================================
== Inicio de la Partida ==

Organizador -> Boundary: presionarIniciarPartida()
Boundary -> Boundary: confirmarInicioJuego()
Boundary -> Control1: iniciarJuego(salaId)
Control1 -> Control3: emit("iniciar-juego", salaId)

Control3 -> Control4: validarEstadoSala(salaId)
Control4 -> Entity1: verificarSala(salaId)
Entity1 -> Control4: salaValidaParaIniciar()
Control4 -> Control3: salaValidaParaIniciar()

Control3 -> Control5: inicializarJuegoVasta(salaData)
Control5 -> Control5: crearEstadoInicial()
Control5 -> Control3: juegoInicializado(estadoInicial)

Control3 -> Control1: emit("juego-iniciado", estadoInicial)
Control1 -> Boundary: recibirInicioJuego(estadoInicial)

Boundary -> Boundary: cerrarPanelAdmin()
Boundary -> Organizador: navegarAPantallaJuego(estadoInicial)

note over Organizador: El organizador ahora participa como jugador más

@enduml
```