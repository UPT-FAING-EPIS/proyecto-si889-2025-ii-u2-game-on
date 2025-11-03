# UC01: Administrar Perfil de Usuario - Diagrama de Secuencia

```plantuml
@startuml
!theme plain
title "Diagrama de Secuencia - UC01: Administrar Perfil de Usuario\n(Boundary - Control - Entity - Actor)"

' === ACTORES ===
actor "👤 Usuario Jugador" as Usuario

' === BOUNDARY ===
participant "🖥️ ProfileScreen\n<<Boundary>>" as Boundary #LightSkyBlue

' === CONTROL ===
participant "⚙️ AuthService\n<<Control>>" as Control1 #LightGreen
participant "🌐 ApiService\n<<Control>>" as Control2 #LightGreen
participant "🖥️ Backend Server\n<<Control>>" as Control3 #LightGreen

' === ENTITY / DATABASE ===
database "🗄️ Firebase Auth\n<<Entity>>" as Entity1 #LightCoral
database "💾 Firebase Firestore\n<<Database>>" as Entity2 #LightCoral

' ====================================================
== Registro de Usuario ==

Usuario -> Boundary: abrirApp()
Boundary -> Control1: verificarSesion()
Control1 -> Boundary: sesionNoExiste()
Boundary -> Usuario: mostrarLoginRegistro()

Usuario -> Boundary: seleccionarRegistro()
Usuario -> Boundary: ingresarCredenciales(email, password)
Boundary -> Control1: validarDatos(email, password)
Control1 -> Boundary: datosValidos()

Boundary -> Control2: registrarUsuario(email, password)
Control2 -> Control3: POST /auth/register
Control3 -> Entity1: createUser(email, password)
Entity1 -> Control3: {uid, token}

Control3 -> Entity2: createDocument("users", userData)
Entity2 -> Control3: documentCreated()
Control3 -> Control2: {success, jwt, userData}
Control2 -> Control1: almacenarToken(jwt)
Control1 -> Boundary: registroExitoso()
Boundary -> Usuario: mostrarMensaje("Registro exitoso")

' ====================================================
== Edición de Perfil ==

Usuario -> Boundary: seleccionarEditarPerfil()
Boundary -> Control1: obtenerDatosUsuario()
Control1 -> Boundary: datosUsuario()
Boundary -> Usuario: mostrarFormularioEdicion()

Usuario -> Boundary: modificarDatos(nombre, avatar)
Usuario -> Boundary: confirmarCambios()
Boundary -> Control1: validarCambios(nuevosDatos)
Control1 -> Boundary: cambiosValidos()

Boundary -> Control2: actualizarPerfil(nuevosDatos)
Control2 -> Control3: PUT /users/profile
Control3 -> Entity2: updateDocument(userId, nuevosDatos)
Entity2 -> Control3: documentUpdated()
Control3 -> Control2: {success, updatedData}
Control2 -> Boundary: perfilActualizado()

Boundary -> Control1: actualizarDatosLocales(updatedData)
Control1 -> Boundary: datosActualizados()
Boundary -> Usuario: mostrarMensaje("Perfil actualizado")
Boundary -> Usuario: mostrarPerfilActualizado()

@enduml
```