# Updates



## Criminal Notification

A new feature now will send a notification to the players in the city. It has a chance check first so it wont always send! Then it checks that the players job is NOT police and will send the notification! This will show minimal info but just enough to give a hint where the Dirty Cop is!

{% code title="server/Sutils.lua" lineNumbers="true" %}
```lua
RegisterNetEvent('SickDirtyCops:NotifyCrimsOfLocation') -- New Event to notify players of Dirty cop location when it moves
AddEventHandler('SickDirtyCops:NotifyCrimsOfLocation', function(street)
    local chance = math.random(0,100) -- chance for the notification to be sent
    if chance < 15 then
        local xPlayers = ESX.GetExtendedPlayers() -- get extended players
        for _, xPlayer in pairs(xPlayers) do
            if not xPlayer.getJob()[Config.PoliceJobName] then -- if players job is not a police job then send message
                if not SentMessage then -- to prevent double messages
                    local NotifData = {
                        title = "Dirty Cop",
                        message = ("Aye I Just picked a new spot! This is to keep cops out of our business! But the new location? Street: %s"):format(street),
                        img= '/html/static/img/icons/messages.png',
                        duration = 7000,
                    }
                    exports["gksphone"]:SendNotification(xPlayer.source, NotifData) -- change to what ever you would like
                    SentMessage = true -- to prevent double messages
                end
            end
        end
        SentMessage = false -- to prevent double messages
    end
end)
```
{% endcode %}
