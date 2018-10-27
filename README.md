# Cable
A fast, easy-to-use net wrapper.

## Installation
1. Drop it anywhere in your project.
2. Drop pON into the same directory as Cable (we recommend using [this one](https://github.com/TeslaCloud/Flux/blob/master/garrysmod/gamemodes/flux/gamemode/vendor/pon.lua))
3. Include it

```lua
if SERVER then
  AddCSLuaFile 'pon.lua'
  AddCSLuaFile 'cable.lua'
end
include 'cable.lua'
```

## Usage
Send a message from server to client:
```lua
if SERVER then
  cable.send(player, 'message_name', 1, false, { 1, 2, 3 })
else
  cable.receive('message_name', function(a, b, c)
    print(a, b, c) -- will print 1 false table
  end)
end
```

Send a message from client to server:
```lua
if SERVER then
  cable.send('message_name', 1, false, { 1, 2, 3 })
else
  cable.receive('message_name', function(a, b, c)
    print(a, b, c) -- will print 1 false table
  end)
end
```
