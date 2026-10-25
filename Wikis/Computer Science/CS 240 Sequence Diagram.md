actor Client
participant Server
participant Handler
participant Service
participant DataAccess
database db

entryspacing 0.9
group#43829c #lightblue Registration
Client -> Server: [POST] /user\n{"username":" ", "password":" ", "email":" "}
Server -> Handler: {"username":" ", "password":" ", "email":" "}
Handler -> Service: register(RegisterRequest)
Service -> DataAccess: getUser(username)
DataAccess -> db:Find UserData by username
break User with username already exists
DataAccess --> Service: UserData
Service --> Server: AlreadyTakenException
Server --> Client: 403\n{"message": "Error: username already taken"}
end
DataAccess --> Service: null
Service -> DataAccess:createUser(userData)
DataAccess -> db:Add UserData
Service -> DataAccess:createAuth(authData)
DataAccess -> db:Add AuthData
Service --> Handler: RegisterResult
Handler --> Server: {"username" : " ", "authToken" : " "}
Server --> Client: 200\n{"username" : " ", "authToken" : " "}
end

group#orange #FCEDCA Login
Client -> Server: [POST] /session\n{"username": " ", "password": " "}
Server->Handler: {"username": " ", "password": " "}
break missing credential
Handler--> Server: MissingCredentialException
Server-->Client:400\n{"message":\n "Please enter a Username and Password"}
end
Handler->Service:LoginRequest(username, password)
Service->DataAccess:findUser(username)
DataAccess->db:Find User by Username

break User Not Found
DataAccess-->Service:null
Service-->Server:UserNotFoundException
Server->Client: 404\n{"message": "User not found"}
end
DataAccess-->Service:{username, password}
Service->Service:VerifyPassword
break Incorrect Password
Service-->Server: IncorrectPasswordException
Server-->Client: 401\n{"message": "Incorrect Username or Password"}
end
Service->DataAccess: writeToken(username)
DataAccess->db:Write AuthToken to DB
Service-->Handler:RequestGranted(username, AuthToken)
Handler-->Server:{"username": " ", "authToken": " "}
Server-->Client:200\n{"username": " ", "authToken": " "}
end

group#green #lightgreen Logout
Client -> Server: [DELETE] /session\nauthToken
Server->Handler: {"authToken": " "}
Handler->Service: Verify(authToken)
Service->DataAccess:FindAuth(auth)
DataAccess->db: Get Auth Token
break Invalid Token
DataAccess-->Service:TokenNotFound
Service-->Server:BadAuthException
Server-->Client: 401\n{"message": "Invalid Credentials"}
end
DataAccess-->Service:AuthToken
Service->DataAccess:DeleteToken(auth)
DataAccess->db:Delete Stored Token
Service-->Server:LogoutSuccess
Server-->Client:200\n{"message": "Successfully Logged Out"}
end

group#red #pink List Games
Client -> Server: [GET] /game\nauthToken
Server->Handler: {"authToken": " "}
Handler->Service: Verify(authToken)
Service->DataAccess:FindAuth(auth)
DataAccess->db: Get Auth Token
break Invalid Token
DataAccess-->Service:TokenNotFound
Service-->Server:BadAuthException
Server-->Client: 401\n{"message": "Invalid Credentials"}
end
DataAccess-->Service: AuthorizedUser
Service-->Handler: Authorized
Handler->Service:ListGames()
Service->DataAccess:GetMatches()
DataAccess->db: Request All Games
break No Existing Games
DataAccess-->Service:null
Service-->Server:NoGamesException
Server-->Client:500\n{"message": "No Saved Games"}
end
DataAccess-->Service: GameMap\n(id,user1,user2,name)
Service-->Handler:ReturnGames(GameMap)
Handler-->Server: {games: {"gameID": 1234, "whiteUsername":"",\n "blackUsername":"", "gameName:""}}
Server-->Client: 200\n{games: {"gameID": 1234, "whiteUsername":"",\n "blackUsername":"", "gameName:""}}
end

group#d790e0 #E3CCE6 Create Game 
Client -> Server: [POST] /game\nauthToken\n{"gameName": " "}
Server->Handler: {"gameName": " "}
break missing data
Handler--> Server: MissingNameException
Server-->Client:400\n{"message":\n "Please enter a Game Name"}
end
Handler->Service: Verify(authToken)
Service->DataAccess:FindAuth(auth)
DataAccess->db: Get Auth Token
break Invalid Token
DataAccess-->Service:TokenNotFound
Service-->Server:BadAuthException
Server-->Client: 401\n{"message": "Invalid Credentials"}
end
DataAccess-->Service: AuthorizedUser
Service-->Handler:Authorized
Handler->Service:GetGame(GameName)
Service->DataAccess:RequestGame(\nGameName)
DataAccess->db: Check if Game Exists
break Game Already Exists
DataAccess-->Service:!null
Service-->Server:GameExistsException
Server-->Client:400\n{"message": "Game Already Exists"}
end
DataAccess-->Service: null
Service->DataAccess:WriteGame(GameName)
DataAccess->db: Write New Game
Service-->Handler:GameID
Handler-->Server:{"GameID": " "}
Server-->Client:200\n{"GameID": }
end

group#yellow #lightyellow Join Game #black
Client -> Server: [PUT] /game\nauthToken\n{playerColor, gameID}
Server->Handler: {playerColor, gameID}
break missing data
Handler--> Server: MissingDataException
Server-->Client:400\n{"message":"Please enter a \nPlayer Color And Game ID"}
end
Handler->Service: Verify(authToken)
Service->DataAccess:FindAuth(auth)
DataAccess->db: Get Auth Token
break Invalid Token
DataAccess-->Service:TokenNotFound
Service-->Server:BadAuthException
Server-->Client: 401\n{"message": "Invalid Credentials"}
end
DataAccess-->Service: AuthorizedUser
Service-->Handler:Authorized
Handler->Service:JoinGame(playerColor, gameID)
Service->DataAccess:GetGameID(GameID)
DataAccess->db:Request Game 
break Game Doesn't Exist
DataAccess-->Service:GameNotFound
Service-->Server:GameNotFoundException
Server-->Client:404\n{"message": "Game Not Found"}
end
DataAccess-->Service:GameData
Service->Service:Add Player to slot
break Slot Already Filled
Service-->Server:PositionUnavailableException
Server-->Client:403\n{"message": "Player Slot Already Filled"}
end
Service->DataAccess: WriteGame
DataAccess->db: Write AuthToken to\nPlayer Color Slot
Service-->Server:JoinSuccess
Server-->Client:200\n{"message": "Successfully Joined Game"}
end

group#gray #lightgray Clear application 
Client -> Server: [DELETE] /db \n{"AdminCommand": "ForceDelete"}
Server -> Handler: {"AdminCommand": "ForceDelete"}
Handler -> db: ClearData(); 
Handler-->Server: SuccessMessage();
Server-->Client: 200 \n{"message": "Database Force Cleared Successfully"}

Client -> Server: [DELETE] /db \n{"AdminCommand": "SafeDelete"}
Server -> Handler: {"AdminCommand": "SafeDelete"}
Handler->Service:ActiveSessionCheck()
Service->DataAccess:ActiveSessionCheck()
DataAccess->db:Get Active Users
break User is currently in session
DataAccess-->Service: ActiveUser = True
Service-->Server: ActiveUserWarning
Server-->Client: Error 500\n{"There is currently a user logged in." Force Delete?"}

end
Handler --> db: ClearData(); 
Handler-->Server: SuccessMessage();
Server-->Client: 200 \n{"message": "Database Cleared Successfully"}
end