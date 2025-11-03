![Logo de mi Cliente](Images/capicodex.png)

![Logo UPT](Images/upt.png)

**UNIVERSIDAD PRIVADA DE TACNA**

**FACULTAD DE INGENIERIA**

**Escuela Profesional de Ingeniería de Sistemas**


` `**<a name="_hlk212818658"></a><a name="_hlk212816530"></a>Proyecto *LastShot - Plataforma de Juegos Sociales Interactivos***

Curso: *Patrones de Software*


Docente: Mag. Patrick Cuadros Quiroga


Integrantes:


***SEBASTIAN NICOLAS FUENTES AVALOS		(2022073902)***

***MAYRA FERNANDA CHIRE RAMOS			(2021072620)***

***GABRIELA LUZKALID GUTIERREZ MAMANI 	(2022074263)***





**Tacna – Perú**

***2025***

**











**Sistema <a name="_hlk212816586"></a>*LastShot - Plataforma de Juegos Sociales Interactivos***

**Informe de Factibilidad**

**Versión *2.0***















|<a name="_hlk212816568"></a>CONTROL DE VERSIONES||||||
| :-: | :- | :- | :- | :- | :- |
|Versión|Hecha por|Revisada por|Aprobada por|Fecha|Motivo|
|1\.0|SFA|GGM|MCR|27/09/2025|Versión Original|
|2\.0|SFA|GGM|MCR|30/10/2025|Versión Original|


# **INDICE GENERAL**



[1.	Descripción del Proyecto	3](#_toc52661346)

[2.	Riesgos	3](#_toc52661347)

[3.	Análisis de la Situación actual	3](#_toc52661348)

[4.	Estudio de Factibilidad	3](#_toc52661349)

[4.1	Factibilidad Técnica	4](#_toc52661350)

[4.2	Factibilidad económica	4](#_toc52661351)

[4.3	Factibilidad Operativa	4](#_toc52661352)

[4.4	Factibilidad Legal	4](#_toc52661353)

[4.5	Factibilidad Social	5](#_toc52661354)

[4.6	Factibilidad Ambiental	5](#_toc52661355)

[5.	Análisis Financiero	5](#_toc52661356)

[6.	Conclusiones	5](#_toc52661357)












**Informe de Factibilidad**

1. <a name="_toc52661346"></a>**Descripción del Proyecto**
   1. **Nombre del proyecto**

LastShot - Plataforma de Juegos Sociales Interactivos

1. **Duración del proyecto**

3 meses

1. **Descripción** 

*LastShot es una aplicación móvil multiplataforma desarrollada en Flutter que ofrece una colección de juegos sociales interactivos diseñados para fomentar la integración social en reuniones y eventos. El sistema integra autenticación de usuarios, comunicación en tiempo real mediante WebSockets, y una arquitectura backend robusta que soporta múltiples sesiones de juego simultáneas.*

**1.4 Objetivos**

<a name="_hlk213015644"></a>       **1.4.1 Objetivo general**

Desarrollar una plataforma móvil integral de juegos sociales interactivos que facilite la integración y entretenimiento en eventos sociales, utilizando tecnologías modernas de desarrollo móvil y comunicación en tiempo real.

`        `**1.4.2 Objetivos Específicos**

- Implementar un sistema de juegos multijugador en tiempo real que soporte hasta 8 jugadores simultáneos con sincronización instantánea de estados de juego.
- Desarrollar una interfaz de usuario intuitiva y atractiva utilizando Flutter que garantice una experiencia fluida en dispositivos Android e iOS.
- Establecer una arquitectura backend escalable con Node.js y Socket.IO que maneje múltiples sesiones de juego concurrentes y gestión de usuarios.

1. <a name="_toc52661347"></a>**Riesgos**
- Latencia de red: Problemas de conectividad que afecten la sincronización en tiempo real de los juegos multijugador.
- Escalabilidad del servidor: Limitaciones en el manejo simultáneo de múltiples sesiones de juego durante picos de usuarios.
- Compatibilidad de dispositivos: Diferencias de rendimiento entre dispositivos móviles de gama baja y alta.
- Dependencia de servicios externos: Fallos en Firebase o servicios de hosting que interrumpan la funcionalidad.
- Actualizaciones de plataforma: Cambios en APIs de Flutter, Android o iOS que requieran modificaciones del código.
1. <a name="_toc52661348"></a>**Análisis de la Situación actual**
   1. **Planteamiento del problema**

      En la actualidad, las reuniones sociales y eventos de integración a menudo carecen de actividades estructuradas que fomenten la participación activa de todos los asistentes. Los juegos tradicionales requieren materiales físicos, preparación previa y pueden ser limitados en cuanto a la cantidad de participantes. Además, muchas aplicaciones de juegos existentes se enfocan en el entretenimiento individual o competencias online con desconocidos, perdiendo el aspecto social presencial. Existe una necesidad de una solución digital que combine la comodidad de la tecnología móvil con la experiencia social de los juegos presenciales.

   1. **Consideraciones de hardware y software**

      Hardware existente disponible:

- Smartphones Android con capacidades estándar de conectividad
- Servidores cloud para hosting y base de datos
- Infraestructura de red inalámbrica estable

Software y tecnologías seleccionadas:

- Flutter para desarrollo multiplataforma
- Node.js con Socket.IO para backend en tiempo real
- Firebase para autenticación y base de datos
- Servicios de hosting cloud (Azure/AWS)

1. <a name="_toc52661349"></a>**Estudio de Factibilidad**
   1. <a name="_toc52661350"></a>**Factibilidad Técnica**

      Hardware:

- Dispositivos móviles con Android 6.0+ o iOS 10+ con mínimo 2 GB de RAM
- Procesadores ARM de gama media-baja (Snapdragon 660+ o A10 Bionic+)
- Conectividad WiFi o datos móviles estable de al menos 5 Mbps
- Servidor cloud con mínimo 4 vCPU y 8 GB RAM para manejo de 100+ usuarios concurrentes
- Almacenamiento SSD de 50 GB para base de datos y archivos del sistema

Software:

- <a name="_hlk213015678"></a>Framework: Flutter 3.0+ para desarrollo multiplataforma
- Backend: Node.js 18+ con Express y Socket.IO para comunicación en tiempo real
- Base de datos: Firebase Firestore para datos de usuarios y MongoDB para logs de juegos
- Autenticación: Firebase Authentication con soporte para email/contraseña
- Hosting: Azure App Service o AWS EC2 para despliegue del backend
- Sistema Operativo: Linux Ubuntu 20.04 LTS para servidores
- Herramientas de desarrollo: VS Code, Android Studio, Xcode (para iOS)

La tecnología seleccionada es ampliamente adoptada, bien documentada y compatible con los requerimientos del proyecto, garantizando la viabilidad técnica de la implementación.

1. <a name="_toc52661351"></a>**Factibilidad Económica**
   1. <a name="_hlk213015393"></a>**Costos Generales** 

Estos costos incluyen gastos operativos básicos necesarios para la implementación del sistema.

|**Material**|**Cantidad**|**Precio Unitario**|**Total**|
| - | - | - | - |
|Paquete de Hojas Bond|1|S/ 6.00|S/ 6.00|
|Lápices|3|S/ 1.60|S/ 4.80|
|**TOTAL**| | |**S/ 10.80**|





Tabla 01: En Costos Generales se detallan las utilidades con sus cantidades y precios haciendo un total de S/10.80.

1. **Costos operativos durante el desarrollo** 

|***Concepto***|***Duración***|***Costo Mensual***|***Costo Final***|
| - | - | - | - |
|*Internet* |*3 meses*|*S/ 90*|*S/ 270*|
|*Energía eléctrica*|*3 meses*|*S/ 70*|*S/ 210*|
|***TOTAL***|* |* |***S/ 480***|

1. **Costos del ambiente**

*Se evalúan costos asociados al entorno tecnológico necesario para la implementación del sistema.*

|<p></p><p>*CONCEPTO*</p>|*DURACIÓN*|*COSTO EN $*|*COSTO EN S/.*|
| - | - | - | - |
|<p>*Azure App Service (Plan Básico B1)*</p><p></p>|*12 meses*|*$104.19*|*S/. 387.61*|
|<p>*Google Play Store (registro desarrollador)*</p><p></p>|<p>*Único*</p><p></p>|<p>*$25.00*</p><p></p>|<p>*S/. 93.00*</p><p></p>|
|***Total***|* |***$104.19***|***S/. 480.61***|

1. **Costos de personal**

*Estos costos corresponden al recurso humano necesario para desarrollar e implementar el sistema de gestión. Incluirán roles como:*
\*\


*●  	Desarrolladores de software para construir y mantener el sistema.*

*●  	Tester o QA para asegurar la calidad del sistema.*

*●  	Diseñador UI/UX para crear una interfaz fácil de usar para el cliente y los empleados.* 

|*ROL*|*DURACIÓN DEL PROYECTO*|*COSTO POR MES*|*COSTO FINAL*|
| - | - | - | - |
|*DevOps*|*3 meses*|*S/. 1200*|*S/. 3600*|
|*Analista de datos*|*3 meses*|*S/. 1200*|*S/. 3600*|
|*Director de proyecto*|*3 meses*|*S/. 1300*|*S/. 3900*|
|***Total***|* |* |***S/. 11100***|

1. **Costos totales del desarrollo del sistema** 

|CONCEPTO|COSTO SOLES|
| - | - |
|Costos Generales|S/ 10.80|
|Costos Operativos|S/. 480|
|Costos de Ambiente|S/. 387.61|
|Costos de Personal|S/. 11200|
|Total|S/. 11,100|


1. <a name="_toc52661352"></a><a name="_hlk213015215"></a>**Factibilidad Operativa**

***Beneficios principales:***

- *Facilitación de actividades de integración social sin requerir materiales físicos*
- *Acceso instantáneo a múltiples juegos desde cualquier smartphone*
- *Reducción de tiempo de preparación para eventos sociales*
- *Escalabilidad automática para diferentes tamaños de grupos*

***Capacidad de operación y mantenimiento:***

- *Sistema autogestionado con mínima intervención manual requerida*
- *Monitoreo automatizado de rendimiento y disponibilidad*
- *Actualizaciones remotas sin interrumpir el servicio*
- *Soporte técnico básico manejable por un desarrollador*

***Impacto en usuarios:***

- *Mejora significativa en la experiencia de eventos sociales*
- *Reducción de la barrera de entrada para participar en juegos grupales*
- *Fomento de la interacción social a través de mecánicas de juego innovadoras*

***Interesados:***

- *Organizadores de eventos sociales y corporativos*
- *Estudiantes universitarios y grupos de amigos*
- *Empresas que buscan actividades de team building*
- *Desarrolladores interesados en contribuir al proyecto open source*


1. <a name="_toc52661353"></a>**Factibilidad Legal**
- ***Ley de Protección de Datos Personales (Ley N° 29733)**: Implementación de políticas de privacidad claras y consentimiento explícito para el tratamiento de datos personales*
- ***Código de Protección y Defensa del Consumidor**: Términos y condiciones transparentes para el uso de la aplicación*
- ***Ley de Delitos Informáticos (Ley N° 30096)**: Medidas de seguridad para prevenir accesos no autorizados y proteger la integridad de los datos*
- ***Regulaciones de INDECOPI**: Cumplimiento con normas de competencia desleal y protección al consumidor digital*
- *No existen restricciones legales específicas para aplicaciones de juegos sociales en Perú*
- *Uso de licencias open source compatibles (MIT/Apache 2.0) para componentes de terceros*

1. <a name="_toc52661354"></a>**Factibilidad Social**

***Aspectos culturales peruanos:***

- *Integración de elementos culturales locales en los juegos (jerga peruana, referencias culturales)*
- *Fomento de la tradición social peruana de reuniones familiares y de amigos*
- *Contribución a la digitalización de entretenimiento social tradicional*
- *Promoción de la inclusión social mediante juegos accesibles para diferentes edades*

***Impacto social positivo:***

- *Reducción de la brecha digital en entretenimiento social*
- *Fortalecimiento de vínculos interpersonales a través de tecnología*
- *Generación de espacios de sana competencia y diversión*

1. <a name="_toc52661355"></a>**Factibilidad Ambiental**

***Impacto ambiental mínimo:***

- *Reducción del uso de materiales físicos para juegos (cartas, dados, tableros)*
- *Menor generación de residuos al digitalizar entretenimiento tradicional*
- *Eficiencia energética mediante arquitectura cloud optimizada*
- *Contribución indirecta a la sostenibilidad al reducir necesidad de producción de juegos físicos*

***Consideraciones de sostenibilidad:***

- *Uso responsable de recursos cloud para minimizar huella de carbono*
- *Optimización de código para reducir consumo de batería en dispositivos móviles*
- *Promoción de reutilización digital versus adquisición de juegos físicos*


1. <a name="_toc52661356"></a>**Análisis Financiero**

1. **Justificación de la Inversión**

***5.1.1 Beneficios* del Proyecto**

***Beneficios Tangibles***

- ***Reducción de costos de entretenimiento**: Eliminación de gastos recurrentes en juegos físicos y materiales*
- ***Ahorro de tiempo en preparación**: Setup instantáneo de juegos sin necesidad de preparación física*
- ***Escalabilidad sin costos adicionales**: Capacidad de agregar más jugadores sin inversión extra en materiales*
- ***Disponibilidad 24/7**: Acceso inmediato a entretenimiento social en cualquier momento y lugar*
- ***Métricas cuantificables**: Datos precisos sobre uso, engagement y preferencias de usuarios*

***Beneficios Intangibles***

- ***Fortalecimiento de relaciones sociales**: Mayor cohesión grupal a través de experiencias compartidas*
- ***Innovación en entretenimiento social**: Posicionamiento como referente en gamificación social*
- ***Mejora en habilidades sociales**: Desarrollo de comunicación y trabajo en equipo*
- ***Satisfacción del usuario**: Experiencias memorables y divertidas en eventos sociales*
- ***Contribución cultural**: Preservación y modernización de tradiciones lúdicas peruanas*
- ***Diferenciación competitiva**: Ventaja única en el mercado de entretenimiento móvil social*

**5.1.2 Criterios de Inversión**

`		`![Analisis Financiero](Images/analisisfinanciero.png)


***5.1.2.1 Relación Beneficio/Costo (B/C)***

*La relación Beneficio/Costo (B/C) del proyecto es de 1.05 Este ratio compara el valor presente de los beneficios con el valor presente de los costos. Un B/C mayor que 1, como en este caso, indica que los beneficios superan ampliamente los costos, lo que hace que el proyecto sea económicamente viable y atractivo para su ejecución.*

`                    `***5.1.2.2 Valor Actual Neto (VAN)***

*El VAN es de S/* 11,645.38*. Esto significa que después de descontar los flujos de efectivo futuros a una tasa de descuento del 10%, el valor presente neto de los ingresos esperados del proyecto es positivo. Un VAN positivo indica que el proyecto generará más valor del que cuesta, por lo tanto, es financieramente viable y debería ser considerado para su implementación.*


***5.1.2.3 Tasa Interna de Retorno (TIR)***

*La Tasa Interna de Retorno (TIR) del proyecto es de 13%, lo cual supera significativamente la tasa de descuento utilizada del 10%. Esta tasa refleja una alta rentabilidad sobre la inversión realizada. Una TIR mayor que la tasa de oportunidad indica que el proyecto no solo es viable, sino que ofrece un retorno atractivo con respecto al riesgo asumido.*

1. <a name="_toc52661357"></a>**Conclusiones**

<a name="_hlk213015439"></a>El análisis de factibilidad del proyecto LastShot indica que es altamente viable y factible desde múltiples perspectivas:

- Técnicamente, el proyecto utiliza tecnologías maduras y ampliamente adoptadas (Flutter, Node.js, Firebase), con requerimientos de hardware accesibles y una arquitectura escalable que garantiza el éxito técnico de la implementación.
- Económicamente, los costos de desarrollo e implementación son moderados (S/. 1,615.22 anuales para infraestructura) en comparación con los beneficios potenciales, especialmente considerando la escalabilidad del modelo digital.
- Operativamente, la solución ofrece beneficios claros tanto para usuarios finales como para organizadores de eventos, con una propuesta de valor sólida y un impacto positivo medible en la experiencia social.
- Legalmente, no existen barreras significativas en el contexto peruano, y el cumplimiento con las regulaciones de protección de datos y derechos del consumidor es perfectamente alcanzable.
- Social y ambientalmente, el proyecto contribuye positivamente a la digitalización del entretenimiento social tradicional, promoviendo la inclusión y reduciendo el impacto ambiental.

La convergencia de estos factores positivos, junto con la creciente adopción de soluciones móviles y la demanda de entretenimiento social digital, confirman que LastShot es un proyecto factible con alto potencial de éxito e impacto positivo en su mercado objetivo.
4

