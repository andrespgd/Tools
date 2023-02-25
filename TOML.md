TOML is NOT intended for serialization of data, unlike YAML or JSON


Good example of a configuration file
```
board_size = 3

[user]
ai_skill = 0.85

[user.player_x]
symbol = "X"
color = "blue"
ai = true

[user.player_o]
symbol = "O"
color = "green"
ai = false

[server]
url = "https://tictactoe.example.com"
```

Python code to read
```
import toml
print (toml.load('tmp.toml'))
```

Will export to output:
```
{
'board_size': 3, 
'user': {'ai_skill': 0.85, 
         'player_x': {'symbol': 'X', 'color': 'blue', 'ai': True}, 
         'player_o': {'symbol': 'O', 'color': 'green', 'ai': False}}, 
 'server': {'url': 'https://tictactoe.example.com'}}
```
