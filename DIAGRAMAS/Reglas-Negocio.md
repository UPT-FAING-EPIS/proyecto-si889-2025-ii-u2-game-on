# Reglas de Negocio - Sistema LastShot

## RN01 - Gestión de Usuarios
- **RN01.1**: Un usuario solo puede tener una sesión activa por dispositivo
- **RN01.2**: El email debe ser único en el sistema para cada usuario
- **RN01.3**: La contraseña debe tener mínimo 6 caracteres
- **RN01.4**: Los nombres de usuario no pueden contener caracteres especiales ofensivos

## RN02 - Salas de Juego Multijugador
- **RN02.1**: Cada sala de juego debe tener un código único de 6 caracteres alfanuméricos
- **RN02.2**: Una sala puede tener máximo 8 jugadores conectados simultáneamente
- **RN02.3**: Solo el organizador (host) puede iniciar el juego
- **RN02.4**: Una sala se elimina automáticamente después de 30 minutos de inactividad
- **RN02.5**: Si el host se desconecta, el siguiente jugador en la lista se convierte en host

## RN03 - Juego VASTA
- **RN03.1**: Cada turno tiene un límite de tiempo de 5 segundos
- **RN03.2**: Si un jugador no responde a tiempo, el juego termina inmediatamente
- **RN03.3**: No se pueden repetir letras en la misma ronda de tema
- **RN03.4**: El tema se selecciona aleatoriamente al iniciar el juego
- **RN03.5**: Cuando se agotan las 26 letras, se cambia automáticamente a un nuevo tema aleatorio
- **RN03.6**: El juego requiere mínimo 2 jugadores para iniciar

## RN04 - Juego El Infiltrado del Bar
- **RN04.1**: Se requiere entre 3-8 jugadores para iniciar el juego
- **RN04.2**: Solo puede haber 1 infiltrado por partida
- **RN04.3**: Los bebedores ganan si eliminan al infiltrado mediante votación
- **RN04.4**: El infiltrado gana si no es descubierto al final del tiempo límite
- **RN04.5**: Cada jugador solo puede votar una vez por ronda de votación

## RN05 - Juegos Solo Device
- **RN05.1**: Los juegos TODITO y YO NUNCA funcionan completamente offline
- **RN05.2**: En TODITO, cada resultado del dado tiene un significado específico (T, O, D, I)
- **RN05.3**: En YO NUNCA, hay exactamente 100 cartas disponibles por sesión
- **RN05.4**: Las cartas de YO NUNCA no se repiten hasta reiniciar el mazo
- **RN05.5**: El mazo de YO NUNCA se puede reiniciar manualmente en cualquier momento

## RN06 - Comunicación en Tiempo Real
- **RN06.1**: Los eventos de juego deben sincronizarse en menos de 500ms entre dispositivos
- **RN06.2**: Si un jugador se desconecta por más de 30 segundos, se considera "fuera del juego"
- **RN06.3**: El sistema debe intentar reconexión automática hasta 3 veces
- **RN06.4**: Los mensajes de error deben mostrarse en jerga peruana amigable

## RN07 - Seguridad y Validación
- **RN07.1**: Todas las comunicaciones deben usar protocolo seguro (HTTPS/WSS)
- **RN07.2**: Los tokens de sesión expiran después de 24 horas de inactividad
- **RN07.3**: No se permite más de 10 intentos de login fallidos por IP en 1 hora
- **RN07.4**: Los datos sensibles del usuario deben encriptarse en la base de datos

## RN08 - Contenido y Localización
- **RN08.1**: Todo el contenido de la aplicación debe estar en español peruano
- **RN08.2**: Las frases de YO NUNCA deben ser apropiadas para audiencia general (no sexual)
- **RN08.3**: Los temas de VASTA incluyen referencias culturales peruanas
- **RN08.4**: Los mensajes de la aplicación usan jerga peruana ("causa", "pata", "chevere")

## RN09 - Rendimiento y Recursos
- **RN09.1**: La aplicación no debe consumir más de 150MB de RAM en dispositivos móviles
- **RN09.2**: Las imágenes y recursos deben optimizarse para conexiones lentas
- **RN09.3**: La aplicación debe funcionar con conexiones de mínimo 1 Mbps
- **RN09.4**: Los logs del sistema se rotan cada 7 días para optimizar almacenamiento

## RN10 - Escalabilidad y Disponibilidad
- **RN10.1**: El sistema debe soportar mínimo 100 usuarios concurrentes
- **RN10.2**: Debe mantener 99.5% de disponibilidad durante horas pico
- **RN10.3**: Los backups automáticos se realizan cada 4 horas
- **RN10.4**: En caso de fallo del servidor, se debe mostrar mensaje informativo al usuario