Description method |Method name |Post or Get | Params                             |Result                                     |
-------------------|------------|------------|------------------------------------|-------------------------------------------|
LogIn or register  |LogIn       |Post        |{Nick, Password }                   |idPlayer if login success <br> -1 else     |
Create table       |CreateTable |Post        |{idPlayer, PlayerPassword, TableName, TablePassword }|idTalbe if create sucsess<br> -1 else|
Join to table      |JoinTable   |Post        |{idPlayer, PlayerPassword, TableName, TablePassword }|idTable if join sucsess<br>-1 else|
Leave table        |LeaveTable  |Post        |{idPlayer, PlayerPassword }         |true if leave sucsess<br>false else        |
Sit at the table   |SitDown     |Post        |{idPlayer, PlayerPassword, numSeat }|true if sit down sucsess<br>false else     |
Get up from the table|StandUp   |Post        |{idPlayer, PlayerPassword }         |true if stand up sucsess<br>false else     |
Force player stand up|ForceStandUp|Post      |{idPlayer, PlayerPassword, idStandingPlayer}|true if force stand up sucsess<br>false else|
Kick player from table|KickPlayer|Post       |{idPlayer, PlayerPassword, idKicksPlayer} |true if kick sucsess<br>false else   |
Change type of game|ChangeGameType|Post      |{idPlayer, PlayerPassword, newGameType } |true if change type of game sucsess<br>false else|
Change count of seats|ChangeSeatsCount|Post  |{idPlayer, PlayerPassword, SeatsCount }|true if change count of seats sucsess<br>false else|
Start game         |StartGame   |Post        |{idPlayer, PlayerPassword }         |true if start game sucsess<br>false else   |
End game           |EndGame     |Post        |{idPlayer, PlayerPassword }         |true if end game sucsess<br>false else     |
Use hint color     |HintColor   |Post        |{idPlayer, PlayerPassword, numPlayer, numColor }|true if use hint sucsess<br>false else|
Use hint number    |HintNumber  |Post        |{idPlayer, PlayerPassword, numPlayer, Number }|true if use hint sucsess<br>false else|
Place card         |PlaceCard   |Post        |{idPlayer, PlayerPassword, numCard }|true if place card sucsess (place card with fall sucsess too)<br>false else|
Drop card          |DropCard    |Post        |{idPlayer, PlayerPassword, numCard }|true if drop card sucsess<br>false else    |
Get all info       |GetInfo     |Get         |idPlayer, PlayerPassword            |see next                                   |

ServerInfo

Name        |Type    |Description                          |
------------|--------|-------------------------------------|
IdPlayer    |int     |id your player                       |
IdTable     |int     |id your table if you joined to table<br>-1 else|
NickById    |Dictionary<int, string>|Get nick by id. Work only for your and your timmets|
Table       |TableInfo|Info about your table if you joined to table<br>null else|

TableInfo

Name        |Type    |Description                          |
------------|--------|-------------------------------------|
Players     |int[]   |List of id players, who joined to table|
Seats       |int[]   |List of id players, who and where sit|
GameStarted |bool    |true if game started<br>false else   |
Game        |GameInfo|Info about your game if game started<br>null else|

GameInfo

Name        |Type    |Description                          |
------------|--------|-------------------------------------|
CurrentPlayer|int    |Number player, who turn now          |
CountHints  |int     |Count of hints                       |
CountFall   |int     |Count of fall                        |
Result      |int     |Current result                       |
GameIsEnd   |bool    |true if game is end<br>false else    |
Table       |int[]   |Current result in every color        |
CurrentGameType|int  |0 = FiveColor, 1 = RainbowIsNewColor, 2 = RainbowIsEvery|
DropsCard   |ICard[] |List of drops card                   |
Players     |PlayersInfo[]|List info about players         |
Story       |Event[] |Story of current game

PlayerInfo

Name        |Type    |Description                          |
------------|--------|-------------------------------------|
Cards       |ICard[] |List of cards on hand                |

ICard

Name        |Type    |Description                          |
------------|--------|-------------------------------------|
Color       |int     |Color of card, if player see this<br>-1 else|
Number      |int     |Number of card, if player see this<br>-1 else|
KnowColor   |int     |What player know about color of this card|
KnowNumber  |int     |What player know about number of this card|

Event

Name        |Type    |Description                          |
------------|--------|-------------------------------------|
Type        |int     |0 - HintColor<br>1 - HintNumber<br>2 - LayOK<br>3 - LayFall<br>4 - Drop|
Color       |int     |Color of card, if place, fall or drop<br>Color used for hint, if color hint<br>-1 else|
Number      |int     |Number of card, if place, fall or drop<br>Number used for hint, if number hint<br>-1 else|
PlayerFrom  |int     |Num of player, who made turn         |
PlayerTo  |int       |Num of player, who recive hint, if hint<br>-1 else|







