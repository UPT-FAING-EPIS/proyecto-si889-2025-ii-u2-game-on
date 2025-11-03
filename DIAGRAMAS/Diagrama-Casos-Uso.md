# Diagrama de Casos de Uso - Sistema LastShot

```plantuml
@startuml
!theme aws-orange

title "Casos de Uso - Sistema LastShot\nInteracción General del Usuario"

left to right direction

actor "Usuario Jugador" as U #lightblue

package "🎯 FUNCIONALIDADES PRINCIPALES" as main_package #lightblue {
  usecase (UC01: Administrar\nPerfil de Usuario) as UC1
  usecase (UC02: Explorar\nJuegos Multijugador) as UC2
  usecase (UC03: Explorar\nJuegos de\nDispositivo Único) as UC3
  usecase (UC04: Administrar\nSala de Juego) as UC4
}

U --> UC1
U --> UC2
U --> UC3
U --> UC4

note bottom of UC2 : "Permite visualizar y unirse\na partidas multijugador"
note bottom of UC3 : "Permite acceder a juegos\npara un solo dispositivo"
note bottom of UC4 : "Crea o gestiona salas\nde juego disponibles"

@enduml
```