# Diagrama de Clases - Sistema LastShot

```plantuml
@startuml
!theme aws-orange
allowmixing

title "Diagrama de Clases - Sistema LastShot\nArquitectura Completa del Sistema"

' === CAPA DE PRESENTACIÓN ===
package "Presentation Layer" #lightblue {
  
  class MainActivity {
    - context: BuildContext
    - authService: AuthService
    + initializeApp(): void
    + checkAuthStatus(): bool
    + navigateToHome(): void
  }
  
  class GamesScreen {
    - availableGames: List<GameType>
    - selectedCategory: GameCategory
    + loadMultiplayerGames(): void
    + loadSoloGames(): void
    + navigateToGame(gameType): void
  }
  
  class ProfileScreen {
    - userProfile: UserModel
    - formController: FormController
    + loadUserData(): void
    + updateProfile(userData): Future<bool>
    + validateForm(): bool
  }
  
  abstract class BaseGameScreen {
    # gameState: GameState
    # socketConnection: SocketService
    + {abstract} initializeGame(): void
    + {abstract} handleGameEvent(event): void
    + showGameResult(result): void
  }
  
  class MultiplayerGameScreen {
    - roomCode: string
    - playersList: List<Player>
    - gameConfig: GameConfiguration
    + createRoom(): Future<string>
    + joinRoom(code): Future<bool>
    + startGame(): void
  }
  
  class SoloGameScreen {
    - currentCard: Card
    - cardDeck: CardDeck
    - animationController: AnimationController
    + loadGame(): void
    + nextCard(): void
    + resetGame(): void
  }
}

' === CAPA DE LÓGICA DE NEGOCIO ===
package "Business Logic Layer" #lightgreen {
  
  class AuthService {
    - firebaseAuth: FirebaseAuth
    - currentUser: UserModel
    - jwtToken: string
    + login(email, password): Future<UserModel>
    + register(userData): Future<UserModel>
    + logout(): Future<void>
    + refreshToken(): Future<string>
  }
  
  class SocketService {
    - connection: WebSocketConnection
    - eventHandlers: Map<string, Function>
    - reconnectAttempts: int
    + connect(url): Future<bool>
    + emit(event, data): void
    + on(event, handler): void
    + disconnect(): void
    + reconnect(): Future<bool>
  }
  
  class GameService {
    - activeGames: Map<string, GameInstance>
    - gameRules: GameRules
    + createGame(type, config): GameInstance
    + joinGame(gameId, player): bool
    + processMove(gameId, move): GameState
    + endGame(gameId): GameResult
  }
  
  class ApiService {
    - baseUrl: string
    - httpClient: HttpClient
    - authHeaders: Map<string, string>
    + get(endpoint): Future<Response>
    + post(endpoint, data): Future<Response>
    + put(endpoint, data): Future<Response>
    + delete(endpoint): Future<Response>
  }
}

' === MODELOS DE DATOS ===
package "Data Models" #lightyellow {
  
  class UserModel {
    + id: string
    + email: string
    + name: string
    + avatar: string
    + createdAt: DateTime
    + lastLogin: DateTime
    + toJson(): Map<string, dynamic>
    + fromJson(json): UserModel
  }
  
  class GameModel {
    + id: string
    + type: GameType
    + name: string
    + description: string
    + minPlayers: int
    + maxPlayers: int
    + isMultiplayer: bool
    + rules: GameRules
  }
  
  class RoomModel {
    + code: string
    + organizerId: string
    + gameType: GameType
    + players: List<Player>
    + config: GameConfiguration
    + status: RoomStatus
    + createdAt: DateTime
  }
  
  class CardModel {
    + id: int
    + text: string
    + category: string
    + difficulty: string
    + gameType: GameType
  }
  
  enum GameType {
    VASTA
    INFILTRADO
    TODITO
    YO_NUNCA
  }
  
  enum RoomStatus {
    WAITING
    CONFIGURING
    PLAYING
    FINISHED
  }
}

' === CAPA DE SERVICIOS BACKEND ===
package "Backend Services" #orange {
  
  class ServerManager {
    - express: ExpressApp
    - socketIO: SocketIOServer
    - port: int
    + initializeServer(): void
    + setupRoutes(): void
    + setupSocketHandlers(): void
    + startServer(): void
  }
  
  class AuthController {
    - firebaseAdmin: FirebaseAdmin
    + register(req, res): Response
    + login(req, res): Response
    + verifyToken(req, res, next): void
    + refreshToken(req, res): Response
  }
  
  class GameController {
    - gameInstances: Map<string, GameInstance>
    + createRoom(req, res): Response
    + joinRoom(req, res): Response
    + getGameState(req, res): Response
    + updateGameConfig(req, res): Response
  }
  
  class VastaGameHandler {
    - activeGames: Map<string, VastaGame>
    - themes: string[]
    + handleCreateRoom(socket, data): void
    + handleJoinRoom(socket, data): void
    + handleStartGame(socket, data): void
    + handlePlayerMove(socket, data): void
  }
  
  class VastaGame {
    - roomId: string
    - players: Player[]
    - currentTheme: string
    - currentLetter: string
    - currentTurn: int
    - timer: Timer
    + startGame(): void
    + nextTurn(): void
    + processAnswer(answer): bool
    + endGame(): GameResult
  }
}

' === CAPA DE INFRAESTRUCTURA ===
package "Infrastructure Layer" #lightcoral {
  
  class FirebaseConfig {
    - apiKey: string
    - authDomain: string
    - projectId: string
    + initializeFirebase(): void
    + getFirestoreInstance(): Firestore
    + getAuthInstance(): FirebaseAuth
  }
  
  interface DatabaseService {
    + create(collection, data): Future<string>
    + read(collection, id): Future<Document>
    + update(collection, id, data): Future<bool>
    + delete(collection, id): Future<bool>
  }
  
  class FirestoreService {
    - firestore: Firestore
    + create(collection, data): Future<string>
    + read(collection, id): Future<Document>
    + update(collection, id, data): Future<bool>
    + delete(collection, id): Future<bool>
  }
  
  cloud AzureAppService {
    + deployedUrl: string
    + environmentVariables: Map
    + scalingConfig: ScalingConfiguration
  }
}

' === RELACIONES PRINCIPALES ===

' Presentation to Business Logic
MainActivity --> AuthService
ProfileScreen --> AuthService
GamesScreen --> GameService
MultiplayerGameScreen --> SocketService
MultiplayerGameScreen --> GameService
SoloGameScreen --> ApiService

' Business Logic Relations
AuthService --> ApiService
GameService --> SocketService
SocketService --> ApiService

' Data Model Usage
AuthService --> UserModel
GameService --> GameModel
MultiplayerGameScreen --> RoomModel
SoloGameScreen --> CardModel

' Backend Relations
ServerManager --> AuthController
ServerManager --> GameController
ServerManager --> VastaGameHandler
VastaGameHandler --> VastaGame

' Infrastructure Relations
AuthService --> FirebaseConfig
ApiService --> AzureAppService
FirestoreService ..|> DatabaseService
AuthController --> FirebaseConfig
GameController --> FirestoreService

' Inheritance
MultiplayerGameScreen --|> BaseGameScreen
SoloGameScreen --|> BaseGameScreen

@enduml
```