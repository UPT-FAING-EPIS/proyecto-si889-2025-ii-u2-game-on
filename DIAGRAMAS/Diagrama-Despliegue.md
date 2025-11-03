# Diagrama de Despliegue - Sistema LastShot

```plantuml
@startuml
!theme plain
title "Diagrama de Despliegue - Sistema LastShot\n(Arquitectura de Infraestructura)"

' === DISPOSITIVO MÓVIL ===
node "📱 Dispositivo Móvil" as DispositivoMovil #lightblue {
  
  artifact "🎮 Flutter App" as FlutterApp #lightgreen
  
  note bottom of FlutterApp : "Características:\n• Plataforma: Android 6.0+\n• Framework: Flutter 3.0+\n• Almacenamiento: 50MB\n• Conectividad: WiFi/4G/5G\n• Funciona offline (juegos solo device)"
}

' === SERVIDOR BACKEND (Azure) ===
node "☁️ Servidor Backend (Azure App Service)" as ServidorBackend #lightyellow {
  
  artifact "🌐 API (Node.js)" as NodeAPI #lightgreen
  
  note bottom of NodeAPI : "Características:\n• Framework: Express.js\n• WebSockets: Socket.IO\n• Autenticación: JWT + Firebase\n• Rate Limiting: 1000 req/min\n• Logs: Winston + Azure Monitor\n• OS: Linux Container\n• Runtime: Node.js 18.x\n• CPU: 1 vCPU, RAM: 1.75 GB"
}

' === SERVICIOS EXTERNOS ===
node "� Servicios Firebase" as ServiciosFirebase #lightcoral {
  
  database "💾 Base de Datos\n(Firestore)" as Firebase #lightsteelblue
  artifact "🔐 Firebase Auth" as FirebaseAuth #lightpink
  
  note bottom of Firebase : "Características:\n• Tipo: NoSQL (Firestore)\n• Región: us-central1\n• Backup automático\n• Escalado automático\n• 99.95% uptime SLA"
  
  note bottom of FirebaseAuth : "Características:\n• Autenticación OAuth\n• JWT Token Management\n• Multi-factor Auth\n• Social Login (Google)"
}

' === CONEXIONES Y COMUNICACIÓN ===

' Flutter App hacia API Backend
FlutterApp --> NodeAPI : "Solicita datos\n(HTTPS/REST)\n(WSS/WebSocket)"

' API hacia Firebase Services
NodeAPI --> Firebase : "Consulta datos\n(Firebase Admin SDK)\n(Firestore API)"

NodeAPI --> FirebaseAuth : "Autenticación\n(Firebase Admin SDK)\n(JWT Verification)"

' === PROTOCOLOS Y PUERTOS ===
note top of FlutterApp : "Protocolos:\n• HTTPS: 443\n• WSS: 443\n• JSON over HTTP"

note top of ServiciosFirebase : "Protocolos:\n• HTTPS: 443\n• Firebase APIs\n• OAuth 2.0"

note top of NodeAPI : "Protocolos:\n• HTTP: 3000\n• WebSocket: 3001\n• Firebase: 443"

@enduml
```