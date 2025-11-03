![Logo de mi Cliente](Images/capicodex.png)

![Logo UPT](Images/upt.png)

**UNIVERSIDAD PRIVADA DE TACNA**

**FACULTAD DE INGENIERIA**

**Escuela Profesional de Ingeniería de Sistemas**


` `**Proyecto *LastShot - Plataforma de Juegos Sociales Interactivos***

Curso: *Patrones de Software*


Docente: Mag. Patrick Cuadros Quiroga


Integrantes:


***SEBASTIAN NICOLAS FUENTES AVALOS		(2022073902)***

***MAYRA FERNANDA CHIRE RAMOS			(2021072620)***

***GABRIELA LUZKALID GUTIERREZ MAMANI 	(2022074263)***





**Tacna – Perú**

***2025***

**

|CONTROL DE VERSIONES||||||
| :-: | :- | :- | :- | :- | :- |
|Versión|Hecha por|Revisada por|Aprobada por|Fecha|Motivo|
|1\.0|SFA|GGM|MCR|27/09/2025|Versión Original|
|2\.0|SFA|GGM|MCR|30/10/2025|Versión Original|











**Sistema *LastShot - Plataforma de Juegos Sociales Interactivos***

**Documento de Visión**

**Versión *2.0***
**\


|CONTROL DE VERSIONES||||||
| :-: | :- | :- | :- | :- | :- |
|Versión|Hecha por|Revisada por|Aprobada por|Fecha|Motivo|
|1\.0|SFA|GGM|MCR|27/09/2025|Versión Original|
|2\.0|SFA|GGM|MCR|30/10/2025|Versión Original|

**ÍNDICE GENERAL**

[**1. Introducción	5**](#_heading=h.2rqyp5odkxy9)

[1.1. Propósito	5](#_heading=h.87zqqgobz7rn)

[1.2. Alcance	5](#_heading=h.28lbs8k1lu1n)

[1.3. Definiciones, Siglas y Abreviaturas	6](#_heading=h.yv2c68asqjv5)

[**2. Posicionamiento	6**](#_heading=h.v0zwe0y1zyus)

[2.1. Oportunidad de negocio	6](#_heading=h.8yczb0wffhle)

[2.2. Definición del problema	7](#_heading=h.ws8hrl1x8wtx)

[**3. Descripción de los interesados y usuarios	7**](#_heading=h.ch69ciwzjnap)

[3.1. Resumen de los interesados	7](#_heading=h.a9run41pzq9x)

[3.2. Resumen de los usuarios	8](#_heading=h.my2n1e6guth5)

[3.3. Entorno de usuario	8](#_heading=h.ibpg5zaoaovs)

[3.4. Perfiles de los interesados	8](#_heading=h.2npar715jj8v)

[3.5. Perfiles de los Usuarios	8](#_heading=h.5lwdnki4ivu8)

[3.6. Necesidades de los interesados y usuarios	9](#_heading=h.7fgyahbetot6)

[**4. Vista General del Producto	9**](#_heading=h.maeaaumvurmv)

[4.1. Perspectiva del producto	9](#_heading=h.vd90d18r46w5)

[4.2. Resumen de capacidades	9](#_heading=h.rkz9vvxbqhlg)

[4.3. Suposiciones y dependencias	9](#_heading=h.xjr0t5aiv01c)

[4.4. Costos y precios	10](#_heading=h.t1prrm0ur3z)

[4.5. Licenciamiento e instalación	10](#_heading=h.vf1450n9jj2c)

[**5. Características del producto	10**](#_heading=h.4553ruuo4nyu)

[**6. Restricciones	10**](#_heading=h.5dlm5c763nuw)

[**7. Rangos de calidad	11**](#_heading=h.zftg0k5x64rf)

[**8. Precedencia y Prioridad	11**](#_heading=h.glzllyilfn5s)

[**9. Otros requerimientos del producto	11**](#_heading=h.ax9qpdsl97yw)

[9.1. Estándares legales	11](#_heading=h.194p9ge8dvsr)

[9.2. Estándares de comunicación	12](#_heading=h.ms67gfclfz9t)

[9.3. Estándares de cumplimiento de la plataforma	12](#_heading=h.ox08d1oxnrne)

[9.4. Estándares de calidad y seguridad	12](#_heading=h.eqcknavzutx)

[**CONCLUSIONES	12**](#_heading=h.fegkvrr7kk4q)

[**RECOMENDACIONES	13**](#_heading=h.2d1afz7im5ni)

[**BIBLIOGRAFÍA	13**](#_heading=h.2j5eqdp64c20)

[WEBGRAFÍA	13](#_heading=h.lzgmti8vaf17)
1. # <a name="_heading=h.2rqyp5odkxy9"></a>**Introducción**
<a name="_hlk213007488"></a>El presente proyecto tiene como propósito desarrollar una aplicación móvil interactiva denominada LastShot, orientada a ofrecer experiencias de juegos multijugador en tiempo real. El sistema está basado en una arquitectura cliente-servidor, donde la comunicación entre los usuarios y el backend se realiza mediante el protocolo WebSocket, permitiendo la transmisión continua de información sin interrupciones y garantizando una interacción fluida durante las partidas.

La aplicación integra una interfaz móvil intuitiva desarrollada con tecnologías modernas y un servidor backend desplegado en la nube a través de Azure App Service, utilizando una pila Node.js para la lógica del servidor y la gestión de eventos. Además, se incorporan servicios de Firebase, como Authentication y Firestore, para asegurar un manejo confiable de las cuentas de usuario, almacenamiento de datos y sincronización de perfiles en línea.

El desarrollo de este sistema busca poner en práctica conceptos fundamentales de la ingeniería de software, tales como el diseño modular, la comunicación en tiempo real, la integración de servicios externos y la seguridad en aplicaciones distribuidas. Asimismo, se enfatiza el uso de herramientas de modelado como PlantUML para representar visualmente los procesos del sistema mediante diagramas de clases, actividades y secuencia, lo que facilita la comprensión de la lógica interna y las interacciones entre los componentes.

En conjunto, este proyecto constituye un ejemplo de cómo la combinación de tecnologías actuales —como Firebase, WebSocket, Azure y Node.js— puede emplearse para construir soluciones escalables, seguras y orientadas a la colaboración entre múltiples usuarios. El resultado final es una aplicación capaz de gestionar perfiles, crear y unir salas de juego, sincronizar eventos en tiempo real y ofrecer una experiencia digital moderna y dinámica.
1. ## **Propósito** 
El propósito del proyecto es desarrollar una plataforma móvil interactiva de juegos sociales que facilite la integración y el entretenimiento en eventos y reuniones presenciales mediante tecnología moderna y accesible.

La finalidad principal es crear una solución digital que combine la comodidad de los dispositivos móviles con la experiencia social de los juegos presenciales, fortaleciendo vínculos interpersonales y eliminando barreras de acceso al entretenimiento grupal.

Este documento tiene como propósito específico:

- Definir la visión general de la plataforma LastShot, sus funcionalidades y su relevancia social.
- Comunicar a los interesados los objetivos y beneficios del proyecto, asegurando un entendimiento común.
- Orientar las fases de diseño, desarrollo y validación, alineando las expectativas de los usuarios con las capacidades técnicas del equipo de trabajo.

En términos prácticos, LastShot servirá como una aplicación móvil multiplataforma que permitirá a grupos de hasta 8 personas disfrutar de juegos interactivos en tiempo real durante reuniones sociales, eventos corporativos y actividades de integración.

Esto contribuirá a mejorar la experiencia social mediante dinámicas estructuradas, participación activa de todos los asistentes y eliminación de la necesidad de materiales físicos.
1. ## <a name="_heading=h.28lbs8k1lu1n"></a>**Alcance**

<a name="_hlk212821598"></a>El alcance del proyecto abarca el desarrollo y despliegue de una aplicación móvil multiplataforma construida en Flutter, diseñada para ofrecer juegos sociales interactivos con comunicación en tiempo real.

**Incluye lo siguiente:**

- Desarrollo de aplicación móvil para Android e iOS utilizando Flutter 3.0+.
- Implementación de sistema de autenticación de usuarios mediante Firebase Authentication.
- Desarrollo de backend en tiempo real con Node.js y Socket.IO para sincronización de juegos multijugador.
- Creación de interfaz de usuario intuitiva y atractiva con soporte para hasta 8 jugadores simultáneos.
- Sistema de salas de juego con códigos de acceso y gestión de sesiones.
- Integración de múltiples juegos sociales interactivos con mecánicas variadas.
- Despliegue en Google Play Store para dispositivos Android.

Con este alcance, el proyecto se enfoca en proporcionar una herramienta de entretenimiento social que facilite la integración grupal en eventos presenciales mediante tecnología móvil moderna.
1. ## <a name="_heading=h.yv2c68asqjv5"></a>**Definiciones, Siglas y Abreviaturas**

- <a name="_hlk213007728"></a>Flutter: Framework de desarrollo multiplataforma de Google para crear aplicaciones móviles nativas.
- Socket.IO: Biblioteca de JavaScript para comunicación en tiempo real bidireccional basada en eventos.
- WebSockets: Protocolo de comunicación que permite conexiones persistentes y bidireccionales.
- Firebase: Plataforma de desarrollo de aplicaciones móviles de Google que proporciona servicios backend.
- Node.js: Entorno de ejecución para JavaScript del lado del servidor.
- Backend: Parte del sistema que gestiona la lógica, base de datos y comunicación del servidor.
- Frontend: Interfaz de usuario con la que interactúan los jugadores en la aplicación móvil.
- UI/UX: User Interface / User Experience (Interfaz de Usuario / Experiencia de Usuario).
- API: Application Programming Interface (Interfaz de Programación de Aplicaciones).
- RAM: Random Access Memory (Memoria de Acceso Aleatorio).
- vCPU: Virtual Central Processing Unit (Unidad Central de Procesamiento Virtual).
1. # <a name="_heading=h.v0zwe0y1zyus"></a>**Posicionamiento**
   1. ## <a name="_heading=h.8yczb0wffhle"></a>**Oportunidad de negocio**

Las reuniones sociales y eventos de integración actuales a menudo carecen de actividades estructuradas que fomenten la participación activa y equitativa de todos los asistentes. Los juegos tradicionales requieren materiales físicos, preparación previa y pueden ser limitados en cuanto a la cantidad de participantes o la variedad de opciones disponibles.

El proyecto representa una oportunidad de innovación tecnológica y social, ya que:

- Permite digitalizar el entretenimiento social tradicional eliminando la necesidad de materiales físicos.
- Facilita a organizadores de eventos y grupos sociales el acceso inmediato a múltiples opciones de juegos sin preparación previa.
- Promueve la integración social mediante mecánicas de juego innovadoras que garantizan la participación de todos.
- Reduce la barrera de entrada para organizar actividades recreativas en reuniones informales y eventos corporativos.
- Puede expandirse a mercados internacionales dada la naturaleza universal del entretenimiento social.
- Contribuye a la modernización de tradiciones lúdicas peruanas mediante elementos culturales locales integrados en los juegos.
  1. ## <a name="_heading=h.ws8hrl1x8wtx"></a>**Definición del problema**

<a name="_hlk212821512"></a>Actualmente, el entretenimiento social en reuniones y eventos presenta las siguientes limitaciones:

- **Dependencia de materiales físicos**: los juegos tradicionales requieren cartas, dados, tableros y otros elementos que deben comprarse, transportarse y prepararse.
- **Tiempo de preparación**: las actividades recreativas exigen planificación previa y setup, restando espontaneidad a las reuniones.
- **Limitaciones de participantes**: muchos juegos físicos están diseñados para cantidades específicas de jugadores, excluyendo a algunos asistentes.
- **Falta de variedad**: adquirir múltiples juegos físicos implica costos elevados y espacio de almacenamiento.
- **Desigualdad en la participación**: en reuniones sin estructura lúdica, algunos asistentes tienden a quedar al margen de las conversaciones.
- **Aplicaciones existentes inadecuadas**: la mayoría de apps de juegos se enfocan en entretenimiento individual o competencias online con desconocidos, perdiendo el aspecto social presencial.

Esto impide contar con una solución digital accesible, versátil y orientada específicamente al fortalecimiento de vínculos interpersonales en contextos presenciales, limitando la calidad de la experiencia social en eventos y reuniones.
1. # <a name="_heading=h.ch69ciwzjnap"></a>**Descripción de los interesados y usuarios**
   1. ## <a name="_heading=h.a9run41pzq9x"></a>**Resumen de los interesados**

- Actualmente, el entretenimiento social en reuniones y eventos presenta las siguientes limitaciones:
- Dependencia de materiales físicos: los juegos tradicionales requieren cartas, dados, tableros y otros elementos que deben comprarse, transportarse y prepararse.
- Tiempo de preparación: las actividades recreativas exigen planificación previa y setup, restando espontaneidad a las reuniones.
- Limitaciones de participantes: muchos juegos físicos están diseñados para cantidades específicas de jugadores, excluyendo a algunos asistentes.
- Falta de variedad: adquirir múltiples juegos físicos implica costos elevados y espacio de almacenamiento.
- Desigualdad en la participación: en reuniones sin estructura lúdica, algunos asistentes tienden a quedar al margen de las conversaciones.
- Aplicaciones existentes inadecuadas: la mayoría de apps de juegos se enfocan en entretenimiento individual o competencias online con desconocidos, perdiendo el aspecto social presencial.
- Esto impide contar con una solución digital accesible, versátil y orientada específicamente al fortalecimiento de vínculos interpersonales en contextos presenciales, limitando la calidad de la experiencia social en eventos y reuniones.
  1. ## <a name="_heading=h.my2n1e6guth5"></a>**Resumen de los usuarios**

- Actualmente, el entretenimiento social en reuniones y eventos presenta las siguientes limitaciones:
- Dependencia de materiales físicos: los juegos tradicionales requieren cartas, dados, tableros y otros elementos que deben comprarse, transportarse y prepararse.
- Tiempo de preparación: las actividades recreativas exigen planificación previa y setup, restando espontaneidad a las reuniones.
- Limitaciones de participantes: muchos juegos físicos están diseñados para cantidades específicas de jugadores, excluyendo a algunos asistentes.
- Falta de variedad: adquirir múltiples juegos físicos implica costos elevados y espacio de almacenamiento.
- Desigualdad en la participación: en reuniones sin estructura lúdica, algunos asistentes tienden a quedar al margen de las conversaciones.
- Aplicaciones existentes inadecuadas: la mayoría de apps de juegos se enfocan en entretenimiento individual o competencias online con desconocidos, perdiendo el aspecto social presencial.
- Esto impide contar con una solución digital accesible, versátil y orientada específicamente al fortalecimiento de vínculos interpersonales en contextos presenciales, limitando la calidad de la experiencia social en eventos y reuniones.
  1. ## <a name="_heading=h.ibpg5zaoaovs"></a>**Entorno de usuario**

LastShot será accesible desde dispositivos móviles Android e iOS mediante descarga desde Google Play Store y posteriormente Apple App Store.

La aplicación contará con:

- Diseño intuitivo y atractivo optimizado para smartphones.
- Interfaz responsiva adaptable a diferentes tamaños de pantalla.
- Funcionamiento en tiempo real con sincronización instantánea entre dispositivos.
- Navegación simple con mínima curva de aprendizaje.
- Soporte para conexión WiFi y datos móviles.
  1. ## <a name="_heading=h.2npar715jj8v"></a>**Perfiles de los interesados**

- Organizadores de eventos sociales y corporativos: requieren variedad de juegos, facilidad de setup y capacidad de personalización para diferentes tipos de audiencia.
- Empresas de recursos humanos: necesitan herramientas de integración que fomenten trabajo en equipo, comunicación efectiva y cohesión grupal.
- Instituciones educativas: buscan actividades recreativas seguras, apropiadas para diferentes edades y que promuevan valores sociales positivos.
- Desarrolladores contribuidores: desean acceso a documentación técnica, APIs claras y comunidad activa para colaborar en el proyecto.
  1. ## **Perfiles de los Usuarios**

- <a name="_hlk212823004"></a>Usuario anfitrión (creador de sala): crea sesiones de juego, genera códigos de acceso, selecciona juegos, gestiona participantes y controla el flujo de las dinámicas.
- Usuario jugador: se une a salas mediante códigos, participa en los juegos, interactúa con otros jugadores y disfruta de la experiencia social.
- Usuario casual: busca entretenimiento rápido sin configuraciones complejas, priorizando simplicidad e inmediatez.
  1. ## <a name="_heading=h.7fgyahbetot6"></a>**Necesidades de los interesados y usuarios**

- Aplicación móvil accesible, intuitiva y con mínima curva de aprendizaje.
- Sistema de salas rápido con códigos de acceso simples y seguros.
- Variedad de juegos sociales con mecánicas diferentes y entretenidas.
- Sincronización en tiempo real sin latencia perceptible (< 500ms).
- Interfaz atractiva con animaciones fluidas y feedback visual claro.
- Compatibilidad con dispositivos Android e iOS de gama media-baja.
- Funcionamiento estable con conexiones WiFi y datos móviles.
- Sistema de perfiles con historial de juegos y estadísticas personales.
- Elementos culturales locales que generen identificación con usuarios peruanos.
- Acceso gratuito sin necesidad de suscripciones o pagos recurrentes.
1. # <a name="_heading=h.maeaaumvurmv"></a>**Vista General del Producto**	
   1. ## <a name="_heading=h.vd90d18r46w5"></a>**Perspectiva del producto**

LastShot será una aplicación móvil multiplataforma desarrollada en Flutter que centraliza el entretenimiento social interactivo mediante juegos en tiempo real.

La plataforma permitirá a grupos de personas presenciales conectarse digitalmente para disfrutar de dinámicas estructuradas, eliminando barreras de acceso relacionadas con materiales físicos, preparación previa y limitaciones de participantes.

El sistema integra frontend móvil, backend en tiempo real y servicios cloud para ofrecer una experiencia fluida, escalable y moderna que fortalece vínculos interpersonales mediante tecnología.
1. ## <a name="_heading=h.rkz9vvxbqhlg"></a>**Resumen de capacidades**

|**Beneficio para el usuario**|**Características que lo soportan**|
| :- | :- |
|Acceso instantáneo a juegos sociales|Sin necesidad de materiales físicos, preparación o compras adicionales|
|Entretenimiento grupal estructurado|Mecánicas de juego diseñadas para garantizar participación equitativa|
|Conexión en tiempo real|Sincronización instantánea mediante WebSockets con latencia < 500ms|
|Setup rápido de sesiones|Creación de salas con códigos simples y acceso inmediato para jugadores|
|Experiencia multiplataforma|Disponible en Android e iOS con interfaz consistente|
|Interfaz intuitiva y atractiva|Diseño moderno con animaciones fluidas y navegación simple|
|Variedad de opciones lúdicas|Múltiples juegos con mecánicas diferentes para distintos contextos sociales|
|Gestión de perfiles|Historial de juegos, estadísticas personales y personalización de avatar|

1. ## <a name="_heading=h.xjr0t5aiv01c"></a>**Suposiciones y dependencias**

**Suposiciones:**

- Los usuarios disponen de smartphones Android 6.0+ o iOS 10+ con 2 GB RAM mínimo.
- Los dispositivos cuentan con conectividad WiFi o datos móviles estable de al menos 5 Mbps.
- Los usuarios están dispuestos a descargar e instalar una aplicación móvil dedicada.
- Las reuniones sociales objetivo ocurren en entornos presenciales con múltiples dispositivos disponibles.

**Dependencias:**

- Servicios de Firebase para autenticación y base de datos en tiempo real.
- Infraestructura cloud (Azure App Service o AWS EC2) para hosting del backend.
- Google Play Store para distribución de la aplicación Android.
- Conectividad a internet constante durante las sesiones de juego.
- Estabilidad de las APIs de Flutter, Socket.IO y servicios de terceros utilizados.
  1. ## **Costos y precios**

La aplicación será de **acceso gratuito** para todos los usuarios sin costos de descarga, suscripciones mensuales ni compras dentro de la app.

Los costos del proyecto están asociados exclusivamente a:

- Desarrollo e implementación: S/. 11,100 (3 meses)
- Infraestructura cloud: S/. 387.61 anuales (Azure App Service Plan Básico B1)
- Registro desarrollador: S/. 93.00 (Google Play Store, pago único)
- Costos operativos: S/. 480 trimestrales (internet y energía eléctrica)

El modelo de negocio prioriza accesibilidad universal y adopción masiva sobre monetización inmediata.
1. ## <a name="_heading=h.vf1450n9jj2c"></a>**Licenciamiento e instalación**

**Licenciamiento:**

- La aplicación móvil será distribuida bajo términos de servicio propios que garanticen protección de datos de usuarios.
- Los componentes de código abierto utilizados (Flutter, Node.js, Socket.IO) mantienen sus licencias originales (MIT/Apache 2.0).
- Los usuarios aceptan términos y condiciones al registrarse, cumpliendo con la Ley N° 29733 de Protección de Datos Personales de Perú.

**Instalación:**

- Descarga directa desde Google Play Store para dispositivos Android.
- Instalación estándar mediante APK con permisos mínimos requeridos (internet, almacenamiento básico).
- Registro de usuario mediante email y contraseña o autenticación anónima opcional.
- Sin necesidad de configuración técnica compleja por parte del usuario.
1. # <a name="_heading=h.4553ruuo4nyu"></a>**Características del producto**
**5.1. Funcionalidades principales**

- **Sistema de autenticación**: registro e inicio de sesión mediante Firebase Authentication con soporte para email/contraseña.
- **Creación de salas de juego**: generación de códigos únicos de 6 caracteres para acceso rápido y seguro.
- **Unión a salas**: ingreso mediante código con validación en tiempo real y lista de jugadores conectados.
- **Gestión de sesiones**: control de jugadores conectados, inicio/finalización de juegos y administración de turnos.
- **Comunicación en tiempo real**: sincronización instantánea de estados de juego mediante WebSockets con latencia < 500ms.
- **Múltiples juegos sociales**: colección diversa de juegos interactivos con mecánicas variadas (preguntas, desafíos, votaciones, roles).
- **Interfaz intuitiva**: navegación simple con feedback visual claro, animaciones fluidas y diseño atractivo.
- **Sistema de perfiles**: avatar personalizable, historial de juegos y estadísticas personales.
- **Chat en sala**: comunicación textual entre jugadores durante las sesiones (opcional).
- **Notificaciones push**: alertas de turnos, eventos importantes y actualizaciones de juego.

**5.2. Características técnicas**

- **Arquitectura cliente-servidor**: frontend móvil Flutter + backend Node.js con separación clara de responsabilidades.
- **Sincronización en tiempo real**: Socket.IO para comunicación bidireccional persistente y actualización instantánea.
- **Escalabilidad horizontal**: soporte para múltiples sesiones concurrentes mediante balanceo de carga.
- **Persistencia de datos**: Firebase Firestore para usuarios y MongoDB para logs de juegos.
- **Compatibilidad multiplataforma**: código compartido entre Android e iOS con adaptaciones específicas de plataforma.
- **Diseño responsivo**: adaptación automática a diferentes tamaños de pantalla y orientaciones.
- **Optimización de rendimiento**: minimización de consumo de batería y datos móviles.
- **Manejo de errores**: reconexión automática ante pérdidas de conectividad y sincronización de estados.
1. # <a name="_heading=h.5dlm5c763nuw"></a>**Restricciones**
<a name="_hlk213007961"></a>**6.1. Restricciones técnicas**

- La aplicación requiere conexión a internet activa durante toda la sesión de juego.
- La sincronización en tiempo real depende de la estabilidad de la conexión de red de los usuarios.
- El rendimiento puede variar en dispositivos de gama muy baja con menos de 2 GB de RAM.
- La versión inicial se publicará únicamente en Google Play Store (Android).
- El backend debe estar alojado en infraestructura cloud con disponibilidad 24/7.
- Las sesiones de juego están limitadas a un máximo de 8 jugadores simultáneos por cuestiones de experiencia de usuario y viabilidad técnica.

**6.2. Restricciones de desarrollo**

- Duración del proyecto limitada a 3 meses según el cronograma establecido.
- Equipo reducido de 3 personas (DevOps, Analista de datos, Director de proyecto).
- Presupuesto total de S/. 12,078.41 que condiciona alcance y funcionalidades.
- Uso obligatorio de tecnologías específicas: Flutter, Node.js, Socket.IO, Firebase.
- Cumplimiento con normativas de protección de datos personales (Ley N° 29733).

**6.3. Restricciones operativas**

- Los usuarios deben disponer de smartphones compatibles (Android 6.0+ o iOS 10+).
- Las sesiones de juego requieren que todos los participantes estén físicamente presentes.
- El sistema no ofrece modo offline ni juego individual.
- La aplicación no incluye matchmaking automático con desconocidos.
1. # <a name="_heading=h.zftg0k5x64rf"></a>**Rangos de calidad**
**7.1. Disponibilidad**

- **Disponibilidad del servicio backend**: mínimo 95% mensual (máximo 36 horas de inactividad al mes).
- **Tiempo de recuperación ante fallos**: máximo 2 horas para restablecer el servicio completo.

**7.2. Rendimiento**

- **Latencia de sincronización**: máximo 500ms entre acción de usuario y actualización en otros dispositivos.
- **Tiempo de carga inicial**: máximo 3 segundos desde apertura de app hasta pantalla principal.
- **Tiempo de conexión a sala**: máximo 2 segundos desde ingreso de código hasta confirmación de acceso.
- **Capacidad del servidor**: soporte para mínimo 100 usuarios concurrentes (12-13 salas simultáneas).

**7.3. Usabilidad**

- **Curva de aprendizaje**: usuarios deben poder crear y unirse a salas en menos de 60 segundos sin tutorial.
- **Tasa de error del usuario**: máximo 5% de acciones que resulten en errores o confusión.
- **Satisfacción del usuario**: mínimo 4.0/5.0 en encuestas de experiencia de usuario.

**7.4. Seguridad**

- **Protección de datos**: encriptación HTTPS para todas las comunicaciones.
- **Autenticación segura**: validación de credenciales mediante Firebase con tokens JWT.
- **Privacidad de salas**: códigos únicos generados aleatoriamente con expiración automática.

**7.5. Mantenibilidad**

- **Código documentado**: mínimo 80% de funciones críticas con documentación inline.
- **Cobertura de pruebas**: mínimo 70% de código cubierto por tests automatizados.
- **Arquitectura modular**: separación clara de componentes para facilitar actualizaciones.
1. # <a name="_heading=h.glzllyilfn5s"></a>**Precedencia y Prioridad**
**8.1. Alta prioridad (Funcionalidades core - MVP)**

- Sistema de autenticación de usuarios (Firebase)
- Creación y unión a salas mediante códigos
- Comunicación en tiempo real con Socket.IO
- Implementación de al menos 3 juegos sociales funcionales
- Interfaz de usuario básica intuitiva
- Gestión de sesiones y turnos de juego
- Sincronización de estados entre dispositivos

**8.2. Media prioridad (Mejoras de experiencia)**

- Sistema de perfiles con avatar personalizable
- Historial de juegos y estadísticas personales
- Notificaciones push para eventos importantes
- Chat textual en salas de juego
- Animaciones y transiciones fluidas
- Elementos culturales peruanos en juegos
- Tutorial interactivo para nuevos usuarios

**8.3. Baja prioridad (Funcionalidades futuras)**

- Publicación en Apple App Store (iOS)
- Modo de juego con roles personalizados
- Sistema de logros y recompensas
- Integración con redes sociales
- Ranking global de jugadores
- Personalización avanzada de salas
- Soporte multiidioma (inglés, quechua)
1. # <a name="_heading=h.ax9qpdsl97yw"></a>**Otros requerimientos del producto**
   1. ## <a name="_heading=h.194p9ge8dvsr"></a>**Estándares legales**

- Ley N° 29733 - Ley de Protección de Datos Personales (Perú): Implementación de políticas de privacidad claras, consentimiento explícito para tratamiento de datos personales y derecho de acceso, rectificación y cancelación de información.
- Código de Protección y Defensa del Consumidor: Términos y condiciones transparentes, información clara sobre el servicio y mecanismos de atención a reclamos.
- Ley N° 30096 - Ley de Delitos Informáticos: Medidas de seguridad para prevenir accesos no autorizados, protección de integridad de datos y denuncia de actividades ilícitas.
- Regulaciones de INDECOPI: Cumplimiento con normas de competencia desleal y protección al consumidor digital.
- Licencias open source: Uso de componentes de terceros bajo licencias compatibles (MIT, Apache 2.0) con correcta atribución.
  1. ## <a name="_heading=h.ms67gfclfz9t"></a>**Estándares de comunicación**

- Protocolo HTTPS: Todas las comunicaciones entre app y servidor mediante conexiones seguras con certificados SSL/TLS.
- WebSockets seguros (WSS): Comunicación en tiempo real encriptada para sincronización de juegos.
- API RESTful: Endpoints documentados siguiendo convenciones REST para operaciones CRUD.
- Formato de datos JSON: Intercambio de información estructurada mediante JSON con esquemas validados.
- Compresión de datos: Optimización de transferencia mediante compresión gzip para reducir consumo de datos móviles.
  1. ## <a name="_heading=h.ox08d1oxnrne"></a>**Estándares de cumplimiento de la plataforma**

- Flutter 3.0+: Uso de versión estable del framework con soporte para Android e iOS.
- Android 6.0 (API 23) o superior: Compatibilidad con el 95%+ de dispositivos Android activos.
- iOS 10 o superior: Compatibilidad con dispositivos iPhone 5S en adelante (planificado para fase 2).
- Google Play Store: Cumplimiento con políticas de publicación, contenido apto para mayores de 12 años.
- Material Design / Cupertino: Adherencia a guías de diseño nativas para consistencia visual.
- Infraestructura cloud certificada: Azure o AWS con estándares ISO/IEC 27001 para seguridad de información.
- Escalabilidad vertical y horizontal: Capacidad de aumentar recursos del servidor según demanda.
  1. ## <a name="_heading=h.eqcknavzutx"></a>**Estándares de calidad y seguridad**

- <a name="_heading=h.fegkvrr7kk4q"></a>Metodología ágil: Desarrollo iterativo con sprints de 2 semanas, retrospectivas y entregas continuas.
- Control de versiones: Uso de Git con convenciones de commits claros y ramas para desarrollo/producción.
- Pruebas automatizadas: Unit tests, integration tests y widget tests para componentes críticos.
- Code review: Revisión de código por pares antes de fusionar cambios a rama principal.
- OWASP Top 10: Implementación de mejores prácticas de seguridad contra vulnerabilidades comunes.
- Logging y monitoreo: Registro de eventos críticos y alertas automáticas ante errores del sistema.
- Backup periódico: Respaldos diarios de base de datos con retención de 30 días.
- Pruebas de estrés: Validación de rendimiento bajo carga con 100+ usuarios concurrentes.
- Auditorías de seguridad: Revisión trimestral de vulnerabilidades y actualizaciones de dependencias.
1. # [**CONCLUSIONES**](#_heading=h.z5igikj69uly)

- El proyecto LastShot aborda una necesidad real en el mercado de entretenimiento social, ofreciendo una solución digital moderna que elimina barreras asociadas a juegos tradicionales físicos.
- La viabilidad técnica está garantizada mediante el uso de tecnologías maduras y ampliamente adoptadas (Flutter, Node.js, Socket.IO, Firebase) con arquitectura escalable y bien documentada.
- Los indicadores financieros positivos (VAN de S/ 11,645.38, TIR de 13%, B/C de 1.05) demuestran la sostenibilidad económica del proyecto con retorno de inversión favorable.
- La propuesta de valor se centra en accesibilidad, inmediatez y fortalecimiento de vínculos sociales, diferenciándose de aplicaciones existentes que priorizan competencia online con desconocidos.
- El alcance definido para 3 meses de desarrollo es realista y alcanzable con el equipo y presupuesto disponibles, priorizando funcionalidades core del MVP.
- El cumplimiento con normativas legales peruanas (Ley N° 29733, INDECOPI) está contemplado desde el diseño del sistema, garantizando protección de datos y transparencia.
- La plataforma tiene potencial de escalabilidad tanto técnica (infraestructura cloud) como de mercado (replicabilidad en otros países, expansión de juegos).
- El enfoque en elementos culturales locales y la identidad peruana genera diferenciación competitiva y mayor identificación con usuarios objetivo.[	](#_heading=h.z5igikj69uly)
1. # <a name="_heading=h.2d1afz7im5ni"></a>[**RECOMENDACIONES**](#_heading=h.vax4lox2mjni)

- <a name="_hlk213015487"></a>Iniciar con un MVP funcional que incluya 3-5 juegos sociales bien pulidos antes de expandir el catálogo, priorizando calidad sobre cantidad.
- Realizar pruebas beta con usuarios reales en eventos sociales y corporativos para validar usabilidad, identificar puntos de fricción y ajustar mecánicas de juego según feedback.
- Establecer alianzas estratégicas con organizadores de eventos, empresas de team building y universidades para promover adopción temprana y generar casos de éxito.
- Implementar sistema de analytics desde el lanzamiento para medir engagement, retención, juegos más populares y comportamiento de usuarios, informando decisiones de producto.
- Diseñar roadmap de contenido con lanzamiento periódico de nuevos juegos (mensual/bimestral) para mantener interés y retención de usuarios activos.
- Evaluar modelo de monetización ético a mediano plazo (juegos premium, personalización avanzada, versión corporativa) sin comprometer accesibilidad básica gratuita.
- Considerar programa de desarrolladores externos que permita a la comunidad contribuir con juegos personalizados siguiendo guías de diseño establecidas.
- Planificar lanzamiento en iOS una vez validado product-market fit en Android, optimizando inversión en registro de Apple Developer Program.
- Documentar lecciones aprendidas durante el desarrollo para facilitar escalabilidad del equipo y transferencia de conocimiento en futuras iteraciones.
- Preparar estrategia de marketing digital enfocada en redes sociales, influencers y boca a boca, aprovechando naturaleza viral del producto en eventos sociales.[	](#_heading=h.vax4lox2mjni)
1. # <a name="_heading=h.2j5eqdp64c20"></a>[**BIBLIOGRAFÍA**](#_heading=h.9sq2xz4hnpom)
   Google. Flutter - Build apps for any screen. Flutter Documentation, 2024. Disponible en: https://flutter.dev

   Socket.IO. Bidirectional and low-latency communication for every platform. Socket.IO Documentation, 2024. Disponible en: https://socket.io/docs

   Firebase. Firebase Documentation - Authentication, Firestore, Cloud Messaging. Google Firebase, 2024. Disponible en: https://firebase.google.com/docs

   Congreso de la República del Perú. Ley N° 29733, Ley de Protección de Datos Personales. Lima: Diario Oficial El Peruano, 2011.

   INDECOPI. Código de Protección y Defensa del Consumidor. Instituto Nacional de Defensa de la Competencia y de la Protección de la Propiedad Intelectual, 2010.

   Congreso de la República del Perú. Ley N° 30096, Ley de Delitos Informáticos. Lima: Diario Oficial El Peruano, 2013.

   Sommerville, Ian. Ingeniería de Software, 10ª edición. Pearson Education, 2016.

   Nielsen, Jakob. Usability Engineering. Morgan Kaufmann Publishers, 1993.[	](#_heading=h.9sq2xz4hnpom)
1. # <a name="_heading=h.lzgmti8vaf17"></a>[**WEBGRAFÍA**](#_heading=h.q4pyf1f6qzac)
   Node.js Foundation. Node.js Documentation. Disponible en: https://nodejs.org/docs

   Google Play Store - Políticas para desarrolladores. Disponible en: https://play.google.com/about/developer-content-policy

   Microsoft Azure. Azure App Service Documentation. Disponible en: https://azure.microsoft.com/documentation

   Amazon Web Services. AWS EC2 Documentation. Disponible en: https://aws.amazon.com/ec2

   Material Design. Design System by Google. Disponible en: https://material.io/design

   OWASP Foundation. OWASP Top Ten - Web Application Security Risks. Disponible en: https://owasp.org/www-project-top-ten

ISO/IEC 27001. Information Security Management. International Organization for Standardization, 2013. Disponible en: https://www.iso.org/isoiec-27001-information-security.html
4

