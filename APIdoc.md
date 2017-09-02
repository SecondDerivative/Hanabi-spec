Description method |Method name |Post or Get | Params                             |Result                                     |
-------------------|------------|------------|------------------------------------|-------------------------------------------|
LogIn or register  |LogIn       |Post        |{Nick, Password }                   |idPlayer if login success <br> -1 else     |
Create table       |CreateTable |Post        |{idPlayer, PlayerPassword, TableName, TablePassword }|idTalbe if create sucsess<br> -1 else|
Join to table      |JoinTable   |Post        |{idPlayer, PlayerPassword, TableName, TablePassword }|true if join sucsess<br>false else|
Leave table        |LeaveTable  |Post        |{idPlayer, PlayerPassword }         |true if leave sucsess<br>false else        |
Sit at the table   |SitDown     |Post        |{idPlayer, PlayerPassword, numSeat }|true if sit down sucsess<br>false else     |
Get up from the table|StandUp   |Post        |{idPlayer, PlayerPassword }         |true if stand up sucsess<br>false else     |
Force player stand up|ForceStandUp|Post      |{idPlayer, PlayerPassword, idStandingPlayer}|true if force stand up sucsess<br>false else|
Kick player from table|KickPlayer|Post       |{idPlayer, PlayerPassword, idKicksPlayer} |true if kick sucsess<br>false else   |
Change type of game|ChangeGameType|Post      |{idPlayer, PlayerPassword, newGameType } |true if change type of game sucsess<br>false else|
Change count of seats|ChangeSeatsCount|Post  |{idPlayer, PlayerPassword, SeatsCount }|true if change count of seats sucsess<br>false else|
Start game         |StartGame   |Post        |{idPlayer, PlayerPassword }         |true if start game sucsess<br>false else   |
End game           |EndGame     |Post        |{idPlayer, PlayerPassword }         |true if end game sucsess<br>false else     |
Use hint color     |HintColor   |Post        |{idPlayer, PlayerPassword, numPlayer, NumColor }|true if use hint sucsess<br>false else|
Use hint number    |HintNumber  |Post        |{idPlayer, PlayerPassword, numPlayer, Number }|true if use hint sucsess<br>false else|
Place card         |PlaceCard   |Post        |{idPlayer, PlayerPassword, numCard }|true if place card sucsess (place card with fall sucsess too)<br>false else|
Drop card          |DropCard    |Post        |{idPlayer, PlayerPassword, numCard }|true if drop card sucsess<br>false else    |
Get all info       |GetInfo     |Get         |idplayer, PlayerPassword            |see next                                   |
