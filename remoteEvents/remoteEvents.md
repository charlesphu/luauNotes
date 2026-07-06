# Remote Events
```lua
-- SERVER fires to client
RemoteEvents.myEvent:FireClient(player, data)
RemoteEvents.myEvent:FireAllClients(data)

-- CLIENT listens
RemoteEvents.myEvent.OnClientEvent:Connect(function(data)
    -- handle it
end)

-- CLIENT fires to server
RemoteEvents.myEvent:FireServer(data)

-- SERVER listens
RemoteEvents.myEvent.OnServerEvent:Connect(function(player, data)
    -- player is injected automatically
end)
```