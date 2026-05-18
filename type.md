# Luau Typing Notes

## Enforce strict typing
use `--!strict` at top of file

## Basic Types

```lua
local a: number = 10
local b: string = "hello"
local c: boolean = true
local d: any = "anything"
```

## Function typing
Basic parameter typing and return type
```lua
local function add(a: number, b: number): number
    return a + b
end
```
Functions with no return type use ()
```lua
local function log(message: string): ()
    print(message)
end
```
Optional Parameters use ?
```lua
local function greet(name: string?)
    print(name or "Guest")
end
```
Functions that crash use never
```lua
local function crash(): never
    error("something went wrong")
end
```

## Tables
Lists type
```lua
local numbers: {number} = {1, 2, 3}
```
Dictionary type
```lua
local inventory: {[string]: number} = {
    apple = 2,
    bread = 5,
}
```
Mixed tables
```lua
local mixed: {number | string} = {1, "hello"}
```

## Structured Tables / OOP
Typing for Classes
```lua
type PlayerData = {
    name: string,
    level: number,
    coins: number,
    isBanned: boolean?,
}
```

## Modules and Classes Pattern
Module side
```lua
local PlayerTracker = {}
PlayerTracker.__index = PlayerTracker

export type Class = {
    player: Player,
    score: number,
    ingInv: {[string]: number},
    tools: {any},
}

function PlayerTracker.New(player: Player): Class
    local self = setmetatable({}, PlayerTracker)

    self.player = player
    self.score = 0
    self.ingInv = {}
    self.tools = {}

    return self
end

return PlayerTracker
```
Importting module class
```lua
local PlayerTrackerModule = require(path)

type PlayerTracker = PlayerTrackerModule.Class
```