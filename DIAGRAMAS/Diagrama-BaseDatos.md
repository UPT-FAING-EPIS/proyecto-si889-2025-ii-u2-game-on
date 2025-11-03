# Diagrama de Base de Datos No Relacional - Sistema LastShot

```plantuml
@startuml
!theme plain
title "Diagrama de Base de Datos No Relacional - Sistema LastShot\n(Firebase Firestore)"

' === COLECCIONES PRINCIPALES ===
package "Firebase Firestore Database" #lightcoral {
  
  json "👥 users" as users {
    "documentId": "user123",
    "fields": {
      "email": "juan.perez@gmail.com",
      "name": "Juan Pérez",
      "avatar": "avatar_01.png",
      "createdAt": "2025-11-02T14:30:00Z",
      "lastLogin": "2025-11-02T15:45:00Z",
      "gamesPlayed": 15,
      "preferences": {
        "soundEnabled": true,
        "notifications": true
      }
    }
  }
  
  json "🎮 gameRooms" as gameRooms {
    "documentId": "room_ABC123",
    "fields": {
      "code": "ABC123",
      "organizerId": "user123",
      "gameType": "VASTA",
      "status": "WAITING",
      "createdAt": "2025-11-02T14:35:00Z",
      "maxPlayers": 8,
      "players": [
        {"id": "user123", "name": "Juan", "ready": true},
        {"id": "user456", "name": "María", "ready": false}
      ],
      "configuration": {
        "timePerTurn": 5,
        "rounds": 10,
        "themes": ["CIUDADES", "ANIMALES"]
      }
    }
  }
  
  json "📊 gameHistory" as gameHistory {
    "documentId": "game_789",
    "fields": {
      "roomCode": "ABC123",
      "gameType": "VASTA",
      "startTime": "2025-11-02T14:40:00Z",
      "endTime": "2025-11-02T14:55:00Z",
      "winners": ["user123"],
      "participants": ["user123", "user456", "user789"],
      "rounds": [
        {
          "theme": "CIUDADES",
          "letter": "M",
          "answers": {
            "user123": "Madrid",
            "user456": "México",
            "user789": null
          }
        }
      ],
      "finalScores": {
        "user123": 85,
        "user456": 70,
        "user789": 45
      }
    }
  }
  
  json "🎯 gameTemplates" as gameTemplates {
    "documentId": "template_vasta",
    "fields": {
      "gameType": "VASTA",
      "name": "Juego VASTA",
      "description": "Encuentra palabras por categoría",
      "minPlayers": 2,
      "maxPlayers": 8,
      "themes": [
        "CIUDADES", "ANIMALES", "COLORES", "COMIDAS",
        "PROFESIONES", "PAÍSES", "DEPORTES", "FRUTAS",
        "NOMBRES", "OBJETOS", "MARCAS", "PELÍCULAS",
        "CANCIONES", "LIBROS", "VIDEOJUEGOS"
      ],
      "defaultConfig": {
        "timePerTurn": 5,
        "rounds": 10,
        "allowReconnect": true
      }
    }
  }
  
  json "🃏 cardDecks" as cardDecks {
    "documentId": "deck_yonunca",
    "fields": {
      "gameType": "YO_NUNCA",
      "totalCards": 100,
      "cards": [
        {
          "id": 1,
          "text": "Yo nunca he cantado en karaoke",
          "category": "entretenimiento",
          "difficulty": "easy"
        },
        {
          "id": 2,
          "text": "Yo nunca he perdido las llaves",
          "category": "vida_diaria",
          "difficulty": "medium"
        }
      ],
      "version": "1.0",
      "lastUpdated": "2025-11-02T10:00:00Z"
    }
  }
}

' === ÍNDICES Y CONSULTAS ===
note top of users : "Índices:\n- email (único)\n- lastLogin (desc)\n- gamesPlayed (desc)"
note top of gameRooms : "Índices:\n- code (único)\n- status + createdAt\n- organizerId"
note top of gameHistory : "Índices:\n- roomCode\n- startTime (desc)\n- participants (array)"

@enduml
```