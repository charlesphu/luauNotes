# Remote Functions
```lua
-- CLIENT invokes server and waits for response
local result = RemoteEvents.myFunction:InvokeServer(data)

-- SERVER handles and returns
RemoteEvents.myFunction.OnServerInvoke = function(player, data)
    -- player is injected automatically
    return true -- returned to client
end

-- SERVER invokes client
local result = RemoteEvents.myFunction:InvokeClient(player, data)

-- CLIENT handles and returns
RemoteEvents.myFunction.OnClientInvoke = function(data)
    return true
end
```