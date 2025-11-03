# Requerimientos del Sistema LastShot

## REQUERIMIENTOS FUNCIONALES

| **ID** | **Nombre** | **Descripción** | **Prioridad** |
|--------|------------|-----------------|---------------|
| **RF01** | **Administrar Perfil de Usuario** | El sistema debe permitir a los usuarios administrar su perfil (registro, login, edición de datos personales, logout) | **ALTA** |
| **RF02** | **Explorar Juegos Multijugador** | El sistema debe permitir explorar y acceder a juegos multijugador (VASTA, El Infiltrado del Bar) con funcionalidades de sala compartida | **ALTA** |
| **RF03** | **Juegos de Dispositivo Único** | El sistema debe proporcionar juegos de dispositivo único (TODITO, YO NUNCA) que funcionen offline con animaciones | **MEDIA** |
| **RF04** | **Administrar Salas de Juego** | El sistema debe permitir administrar salas de juego (crear, configurar, invitar, gestionar participantes) | **ALTA** |
| **RF05** | **Comunicación en Tiempo Real** | El sistema debe implementar comunicación en tiempo real mediante WebSockets para sincronización de estados | **ALTA** |
| **RF06** | **Generación de Códigos QR** | El sistema debe generar códigos QR para facilitar el acceso y compartir la aplicación | **MEDIA** |
| **RF07** | **Manejo de Desconexiones** | El sistema debe manejar desconexiones automáticamente y permitir reconexión sin pérdida de progreso | **ALTA** |

## REQUERIMIENTOS NO FUNCIONALES

| **ID** | **Nombre** | **Descripción** | **Prioridad** |
|--------|------------|-----------------|---------------|
| **RNF01** | **Rendimiento** | Tiempo de respuesta < 200ms para acciones locales y < 500ms para sincronización de red | **ALTA** |
| **RNF02** | **Usabilidad** | Interfaz intuitiva con jerga peruana familiar y iconos universalmente reconocibles | **ALTA** |
| **RNF03** | **Compatibilidad** | Compatible con Android 6.0+ (API 23+) e iOS 10.0+, soporte para WiFi y datos móviles | **ALTA** |
| **RNF04** | **Confiabilidad** | Disponibilidad del 99.5%, recuperación automática ante fallos, manejo robusto de errores | **ALTA** |
| **RNF05** | **Seguridad** | Encriptación HTTPS/WSS, validación de entrada, autenticación JWT, cumplimiento GDPR | **ALTA** |
| **RNF06** | **Mantenibilidad** | Código modular, documentación completa, logging detallado, arquitectura escalable | **MEDIA** |
| **RNF07** | **Portabilidad** | Flutter multiplataforma, backend Node.js independiente, Firebase cloud, despliegue multi-cloud | **MEDIA** |