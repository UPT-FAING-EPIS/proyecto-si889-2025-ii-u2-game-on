# Diagrama de Componentes - Sistema LastShot

```plantuml
@startuml
!theme plain
title "Diagrama de Componentes - Sistema LastShot\n(Vista Arquitectural)"

' === COMPONENTES FRONTEND ===
package "Frontend Components" #lightblue {
  
  component "📱 Flutter App" as FlutterApp {
    port "HTTP" as FlutterHTTP
    port "WebSocket" as FlutterWS
  }
  
  component "🖥️ UI Components" as UIComponents
  component "⚙️ Business Logic" as BusinessLogic
  component "💾 Local Storage" as LocalStorage
  
  FlutterApp --> UIComponents
  FlutterApp --> BusinessLogic
  BusinessLogic --> LocalStorage
}

' === COMPONENTES BACKEND ===
package "Backend Components" #orange {
  
  component "🌐 Node.js API Server" as NodeAPI {
    port "REST API" as RestPort
    port "WebSocket Server" as WSPort
  }
  
  component "🔐 Auth Module" as AuthModule
  component "🎮 Game Engine" as GameEngine
  component "🔌 Socket Handlers" as SocketHandlers
  
  NodeAPI --> AuthModule
  NodeAPI --> GameEngine
  NodeAPI --> SocketHandlers
}

' === COMPONENTES DE DATOS ===
package "Data Components" #lightcoral {
  
  component "🔥 Firebase Auth" as FirebaseAuth {
    port "Auth API" as AuthAPI
  }
  
  component "💾 Firebase Firestore" as Firestore {
    port "Database API" as DbAPI
  }
  
  component "📊 Game Data Manager" as GameDataManager
  
  GameDataManager --> Firestore
  AuthModule --> FirebaseAuth
}

' === COMPONENTES DE INFRAESTRUCTURA ===
package "Infrastructure Components" #lightyellow {
  
  component "☁️ Azure App Service" as AzureService
  component "🌐 Load Balancer" as LoadBalancer
  component "📈 Monitoring" as Monitoring
  
  AzureService --> LoadBalancer
  AzureService --> Monitoring
}

' === CONEXIONES ENTRE COMPONENTES ===

' Frontend to Backend
FlutterHTTP --> RestPort : HTTP/HTTPS
FlutterWS --> WSPort : WebSocket/WSS

' Backend to Data
RestPort --> DbAPI : Firestore SDK
AuthModule --> AuthAPI : Firebase Admin SDK

' Backend to Infrastructure
NodeAPI --> AzureService : Deployed on

' Internal Dependencies
BusinessLogic --> GameDataManager : Game State
SocketHandlers --> GameEngine : Real-time Updates

@enduml
```