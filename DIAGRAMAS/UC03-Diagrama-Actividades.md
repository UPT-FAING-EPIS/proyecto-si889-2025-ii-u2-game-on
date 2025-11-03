# UC03: Explorar Juegos de Dispositivo Único - Diagrama de Actividades

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
|#ddeeff|Usuario|
|#e6ffe6|Aplicación Mobile|
|#fffbe6|Local Storage|
|#ffe6e6|Animation Engine|

title "Diagrama de Actividades - UC03: Explorar Juegos de Dispositivo Único"

|Usuario|
start
:Accede a sección "Juegos Solo Device";

|Aplicación Mobile|
:Carga juegos desde memoria local;
:Muestra lista [TODITO, YO NUNCA];

|Usuario|
:Selecciona "YO NUNCA";

|Aplicación Mobile|
:Verifica que NO requiere conexión de red;

|Local Storage|
:Carga configuración del juego;
:Recupera progreso guardado (si existe);

|Aplicación Mobile|
:Inicializa mazo de 100 cartas;
:Selecciona primera carta aleatoria;

|Animation Engine|
:Prepara animación de entrada;
:Reproduce efecto de sonido;

|Aplicación Mobile|
:Muestra carta con animación;
:Muestra contador de cartas;

|Usuario|
:Lee la carta: "Yo nunca he cantado en karaoke";

if (¿Usuario quiere siguiente carta?) then (sí)
  |Usuario|
  :Toca la pantalla para continuar;
  
  |Aplicación Mobile|
  :Marca carta actual como usada;
  
  |Local Storage|
  :Guarda progreso actualizado;
  
  |Aplicación Mobile|
  :Selecciona nueva carta aleatoria;
  :Verifica que no esté repetida;
  
  |Animation Engine|
  :Ejecuta animación de transición;
  :Reproduce sonido de cambio;
  
  |Aplicación Mobile|
  :Muestra nueva carta;
  :Actualiza contador;
  
  if (¿Quedan cartas disponibles?) then (sí)
    :Continúa con nueva carta;
  else (no)
    :Muestra mensaje "Mazo completado";
    :Ofrece opción de reiniciar;
    
    if (¿Usuario quiere reiniciar?) then (sí)
      |Local Storage|
      :Reinicia progreso del juego;
      
      |Aplicación Mobile|
      :Reinicializa mazo completo;
      :Vuelve a carta inicial;
    else (no)
      |Usuario|
      :Regresa al menú principal;
      stop
    endif
  endif
else (no)
  if (¿Usuario quiere cambiar juego?) then (sí)
    |Usuario|
    :Selecciona "TODITO";
    
    |Aplicación Mobile|
    :Carga juego del dado virtual;
    :Muestra dado en pantalla;
    
    |Usuario|
    :Toca el dado para lanzar;
    
    |Animation Engine|
    :Anima rotación del dado;
    :Reproduce sonido de dados;
    
    |Aplicación Mobile|
    :Genera número aleatorio (1-6);
    :Muestra resultado del dado;
    
    |Local Storage|
    :Guarda estadísticas del juego;
    
  else (no)
    |Usuario|
    :Sale de los juegos solo device;
    stop
  endif
endif

@enduml

```