# UC03: Explorar Juegos de Dispositivo Único - Diagrama de Secuencia

```plantuml
@startuml
!theme plain
title "Diagrama de Secuencia - UC03: Explorar Juegos de Dispositivo Único\n(Boundary - Control - Entity - Actor)"

' === ACTORES ===
actor "👤 Usuario Jugador" as Usuario

' === BOUNDARY ===
participant "🖥️ SoloGameScreen\n<<Boundary>>" as Boundary #LightSkyBlue

' === CONTROL ===
participant "🎮 YoNuncaGame\n<<Control>>" as Control1 #LightGreen
participant "🃏 MazoCartas\n<<Control>>" as Control2 #LightGreen
participant "🎬 AnimationController\n<<Control>>" as Control3 #LightGreen
participant "🔊 AudioManager\n<<Control>>" as Control4 #LightGreen

' === ENTITY / DATABASE ===
database "💾 LocalStorage\n<<Database>>" as Entity1 #LightCoral

' ====================================================
== Acceso a Juegos Solo Device ==

Usuario -> Boundary: accederJuegosSoloDevice()
Boundary -> Entity1: cargarJuegosDisponibles()
Entity1 -> Boundary: listaJuegos([TODITO, YO NUNCA])
Boundary -> Usuario: mostrarOpcionesJuego()

' ====================================================
== Selección y Inicio de YO NUNCA ==

Usuario -> Boundary: seleccionarJuego("YO NUNCA")
Boundary -> Control1: inicializarJuego()
Control1 -> Entity1: cargarProgreso("YO NUNCA")
Entity1 -> Control1: progresoGuardado(cartaActual, cartasUsadas)

Control1 -> Control2: inicializarMazo(100)
Control2 -> Control1: mazoInicializado()

Control1 -> Control2: obtenerCartaAleatoria(cartasUsadas)
Control2 -> Control1: carta(id: 13, texto: "Yo nunca he cantado en karaoke")

Control1 -> Control3: prepararAnimacionEntrada()
Control3 -> Control4: reproducirSonido("card-appear.mp3")
Control4 -> Control3: sonidoReproducido()

Control3 -> Boundary: mostrarCartaConAnimacion(carta)
Boundary -> Usuario: mostrarCarta("Yo nunca he cantado en karaoke")

' ====================================================
== Navegación entre Cartas ==

Usuario -> Boundary: tocarPantalla()
Boundary -> Control1: siguienteCarta()

Control1 -> Entity1: guardarProgreso(cartaActual: 13)
Entity1 -> Control1: progresoGuardado()

Control1 -> Control2: obtenerNuevaCarta(cartasUsadas)
Control2 -> Control2: verificarNoRepetida(cartasUsadas)
Control2 -> Control1: nuevaCarta(id: 47, texto: "Yo nunca he perdido las llaves")

Control1 -> Control3: ejecutarTransicion("slide-left")
Control3 -> Control4: reproducirSonido("card-flip.mp3")
Control4 -> Control3: sonidoReproducido()

Control3 -> Boundary: mostrarNuevaCarta(carta)
Boundary -> Usuario: mostrarCartaActualizada()

' ====================================================
== Finalización o Reinicio ==

loop Hasta completar mazo o salir
    Usuario -> Boundary: continuarJuego()
    Boundary -> Control1: procesarAccion()
end

alt Mazo completado
    Control1 -> Boundary: mostrarMensaje("¡Mazo completado!")
    Boundary -> Usuario: ofrecerReinicio()
    
    Usuario -> Boundary: seleccionarReinicio()
    Boundary -> Control1: reiniciarJuego()
    Control1 -> Entity1: limpiarProgreso()
    Entity1 -> Control1: progresoLimpiado()
    Control1 -> Control2: reinicializarMazo()
    Control2 -> Control1: mazoReiniciado()
    
else Usuario sale del juego
    Usuario -> Boundary: salirDelJuego()
    Boundary -> Entity1: guardarEstadoFinal()
    Entity1 -> Boundary: estadoGuardado()
end

@enduml
```