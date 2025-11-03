[![Review Assignment Due Date](https://classroom.github.com/assets/deadline-readme-button-22041afd0340ce965d47ae6ef1cefeee28c7c493a6346c4f15d667ab976d596c.svg)](https://classroom.github.com/a/cfr5xe4p)
[![Open in Codespaces](https://classroom.github.com/assets/launch-codespace-2972f46106e565e64193e422d61a12cf1da4916b45550586e14ef0a7c637dd04.svg)](https://classroom.github.com/open-in-codespaces?assignment_repo_id=20934295)

# 🎮 LastShot - Plataforma de Juegos Multijugador

## 📋 Descripción del Proyecto

**LastShot** es una aplicación móvil desarrollada en Flutter que permite a los usuarios disfrutar de juegos de mesa digitales tanto en modo multijugador (en tiempo real) como en modo dispositivo único (offline). La plataforma incluye juegos populares como VASTA, El Infiltrado del Bar, TODITO y YO NUNCA.

### 🏗️ Arquitectura del Sistema
- **Frontend:** Flutter (Android 6.0+)
- **Backend:** Node.js + Express.js + Socket.IO
- **Base de Datos:** Firebase Firestore (NoSQL)
- **Autenticación:** Firebase Authentication + JWT
- **Despliegue:** Azure App Service
- **Comunicación:** REST API + WebSockets para tiempo real

---

## 🚀 Guía de Despliegue

### 📋 Requisitos del Sistema

#### 💻 Requisitos de Desarrollo
- **Node.js:** >= 18.0.0
- **Flutter:** >= 3.0.0
- **Dart SDK:** >= 2.19.0
- **Android Studio:** Latest version
- **Git:** Para control de versiones
- **Firebase CLI:** Para configuración de servicios

#### 📱 Requisitos del Dispositivo Móvil
- **Sistema Operativo:** Android 6.0 (API 23) o superior
- **RAM:** Mínimo 2GB, recomendado 4GB
- **Almacenamiento:** 100MB libres para la aplicación
- **Conectividad:** WiFi o datos móviles (opcional para juegos offline)

#### ☁️ Requisitos de Infraestructura
- **Azure App Service:** Plan B1 o superior
- **Firebase Project:** Plan Spark (gratuito) o Blaze (pago por uso)
- **Certificado SSL:** Incluido en Azure App Service

---

## 🔧 Procedimiento de Instalación

### 1️⃣ Configuración del Entorno

```bash
# Clonar el repositorio
git clone https://github.com/UPT-FAING-EPIS/lastshot.git
cd lastshot

# Instalar dependencias del backend
cd lastshotbackend
npm install

# Instalar dependencias del frontend
cd ../lastshot
flutter pub get
```

### 2️⃣ Configuración de Firebase

```bash
# Instalar Firebase CLI
npm install -g firebase-tools

# Login a Firebase
firebase login

# Inicializar proyecto Firebase
firebase init

# Configurar Firestore Security Rules
firebase deploy --only firestore:rules

# Configurar Firebase Functions (opcional)
firebase deploy --only functions
```

#### 📝 Configuración de Variables de Entorno

Crear archivo `.env` en la carpeta `lastshotbackend/`:

```env
# Firebase Configuration
FIREBASE_PROJECT_ID=your-project-id
FIREBASE_PRIVATE_KEY=your-private-key
FIREBASE_CLIENT_EMAIL=your-client-email

# Server Configuration
PORT=3000
NODE_ENV=production
JWT_SECRET=your-jwt-secret

# Azure Configuration
AZURE_STORAGE_CONNECTION=your-azure-connection
```

### 3️⃣ Configuración del Backend (Node.js)

```bash
cd lastshotbackend

# Instalar dependencias
npm install express socket.io firebase-admin cors helmet dotenv

# Configurar estructura de archivos
mkdir -p src/routes src/middleware src/sockets src/config

# Ejecutar en modo desarrollo
npm run dev

# Ejecutar en modo producción
npm start
```

#### 📦 Estructura de Archivos Backend
```
lastshotbackend/
├── src/
│   ├── server.js           # Servidor principal
│   ├── config/
│   │   └── firebase.js     # Configuración Firebase
│   ├── routes/
│   │   ├── auth.js         # Rutas de autenticación
│   │   ├── games.js        # Rutas de juegos
│   │   └── users.js        # Rutas de usuarios
│   ├── sockets/
│   │   ├── gameHandlers.js # Handlers WebSocket
│   │   └── vastaHandlers.js# Handlers específicos VASTA
│   └── middleware/
│       ├── auth.js         # Middleware de autenticación
│       └── validation.js   # Validación de datos
├── package.json
└── .env
```

### 4️⃣ Configuración del Frontend (Flutter)

```bash
cd lastshot

# Configurar Firebase para Flutter
flutter pub add firebase_core firebase_auth cloud_firestore

# Configurar dependencias adicionales
flutter pub add socket_io_client http qr_flutter

# Generar archivos de configuración
flutter packages pub run build_runner build

# Ejecutar en emulador/dispositivo
flutter run

# Compilar APK para producción
flutter build apk --release
```

#### 🔧 Configuración Firebase en Flutter

Crear archivo `lib/firebase_options.dart`:

```dart
import 'package:firebase_core/firebase_core.dart' show FirebaseOptions;
import 'package:flutter/foundation.dart' show defaultTargetPlatform, kIsWeb, TargetPlatform;

class DefaultFirebaseOptions {
  static FirebaseOptions get currentPlatform {
    switch (defaultTargetPlatform) {
      case TargetPlatform.android:
        return android;
      default:
        throw UnsupportedError('FirebaseOptions not configured');
    }
  }

  static const FirebaseOptions android = FirebaseOptions(
    apiKey: 'your-api-key',
    appId: 'your-app-id',
    messagingSenderId: 'your-sender-id',
    projectId: 'your-project-id',
    storageBucket: 'your-storage-bucket',
  );
}
```

---

## ⚙️ Parámetros de Configuración

### 🔐 Configuración de Autenticación

```javascript
// Backend: middleware/auth.js
const JWT_EXPIRY = '24h';
const REFRESH_TOKEN_EXPIRY = '7d';
const MAX_LOGIN_ATTEMPTS = 5;
const LOCKOUT_TIME = 15; // minutos
```

### 🎮 Configuración de Juegos

```javascript
// Backend: config/games.js
const GAME_CONFIG = {
  VASTA: {
    MAX_PLAYERS: 8,
    MIN_PLAYERS: 2,
    TURN_TIMEOUT: 5000, // 5 segundos
    THEMES: ['CIUDADES', 'ANIMALES', 'COLORES', 'COMIDAS'],
    DEFAULT_ROUNDS: 10
  },
  INFILTRADO: {
    MAX_PLAYERS: 8,
    MIN_PLAYERS: 3,
    DISCUSSION_TIME: 180000, // 3 minutos
    VOTING_TIME: 60000 // 1 minuto
  }
};
```

### 📡 Configuración WebSocket

```javascript
// Backend: server.js
const SOCKET_CONFIG = {
  cors: {
    origin: ['http://localhost:3000', 'https://your-app-domain.com'],
    methods: ['GET', 'POST']
  },
  pingTimeout: 60000,
  pingInterval: 25000,
  maxHttpBufferSize: 1e6
};
```

### 🗄️ Configuración Base de Datos

```javascript
// Firestore Security Rules
rules_version = '2';
service cloud.firestore {
  match /databases/{database}/documents {
    // Usuarios autenticados pueden leer/escribir sus datos
    match /users/{userId} {
      allow read, write: if request.auth != null && request.auth.uid == userId;
    }
    
    // Salas de juego públicas para lectura, escritura solo para participantes
    match /gameRooms/{roomId} {
      allow read: if request.auth != null;
      allow write: if request.auth != null && 
        request.auth.uid in resource.data.players;
    }
  }
}
```

---

## 🚢 Despliegue en Producción

### ☁️ Despliegue Backend (Azure App Service)

```bash
# Preparar para despliegue
npm run build

# Crear archivo web.config para Azure
echo '<?xml version="1.0" encoding="utf-8"?>
<configuration>
  <system.webServer>
    <handlers>
      <add name="iisnode" path="src/server.js" verb="*" modules="iisnode"/>
    </handlers>
    <rewrite>
      <rules>
        <rule name="DynamicContent">
          <match url="/*" />
          <action type="Rewrite" url="src/server.js"/>
        </rule>
      </rules>
    </rewrite>
  </system.webServer>
</configuration>' > web.config

# Desplegar usando Azure CLI
az webapp deployment source config-zip \
  --resource-group lastshot-rg \
  --name lastshot-backend \
  --src backend.zip
```

### 📱 Despliegue Frontend (Google Play Store)

```bash
# Compilar APK firmado
flutter build apk --release

# Generar App Bundle para Play Store
flutter build appbundle --release

# El archivo se generará en: build/app/outputs/bundle/release/app-release.aab
```

---

**🎮 ¡Disfruta jugando con LastShot!** 🚀