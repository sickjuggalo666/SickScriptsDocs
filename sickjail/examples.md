# Examples



{% tabs %}
{% tab title="ESX Ambulance Job" %}
```lua
CreateThread(function()
    local text, timeHeld\n
    while earlySpawnTimer > 0 and isDead do
        Wait(0)
        text = _U('respawn_available_in', secondsToClock(earlySpawnTimer))\n
        DrawGenericTextThisFrame()
        BeginTextCommandDisplayText('STRING')
        AddTextComponentSubstringPlayerName(text)
        EndTextCommandDisplayText(0.5, 0.8)
    end\n
    while bleedoutTimer > 0 and isDead do
    Wait(0)
    text = _U('respawn_bleedout_in', secondsToClock(bleedoutTimer))
    if not Config.EarlyRespawnFine then
        text = text .. _U('respawn_bleedout_prompt')
        if IsControlPressed(0, 38) and timeHeld > 120 then
        
            local inJail = exports['SickJail']:GetJailTime()
            if inJail then
                exports['SickJail']:DeathJailLogin()
                break
            else
                RemoveItemsAfterRPDeath()
                break
            end
        end
    elseif Config.EarlyRespawnFine and canPayFine then
        text = text .. _U('respawn_bleedout_fine', ESX.Math.GroupDigits(Config.EarlyRespawnFineAmount))
        if IsControlPressed(0, 38) and timeHeld > 120 then
            local inJail = exports['SickJail']:GetJailTime()
            if inJail then
                exports['SickJail']:DeathJailLogin()
                break
            else
                TriggerServerEvent('esx_ambulancejob:payFine')
                RemoveItemsAfterRPDeath()
                break
            end
        end
    end
    if IsControlPressed(0, 38) then
        timeHeld += 1
    else
        timeHeld = 0
    end
    DrawGenericTextThisFrame()
    BeginTextCommandDisplayText('STRING')
    AddTextComponentSubstringPlayerName(text)
    EndTextCommandDisplayText(0.5, 0.8)
    if bleedoutTimer < 1 and isDead then
        RemoveItemsAfterRPDeath()
    end
end)
```
{% endtab %}

{% tab title="Wasabi Ambulance" %}
```lua
CreateThread(function()
    local text, timeHeld
    while earlySpawnTimer > 0 and isDead do
        Wait()
        text = (Strings.respawn_available_in):format(secondsToClock(earlySpawnTimer))
        DrawGenericTextThisFrame()
        SetTextEntry('STRING')
        AddTextComponentString(text)
        DrawText(0.5, 0.8)
    end
    while bleedoutTimer > 0 and isDead do
        Citizen.Wait()
        text = (Strings.respawn_bleedout_in):format(secondsToClock(bleedoutTimer)) .. Strings.respawn_bleedout_prompt
        if IsControlPressed(0, 38) and timeHeld > 60 then
            local inJail = exports['SickJail']:GetJailTime()
            if inJail then
                exports['SickJail']:DeathJailLogin()
                break
            else
                StartRPDeath()
                break
            end
        end
        if IsControlPressed(0, 38) then
            timeHeld = timeHeld + 1
        else
            timeHeld = 0
        end
        DrawGenericTextThisFrame()
        SetTextEntry('STRING')
        AddTextComponentString(text)
        DrawText(0.5, 0.8)
    end
    if bleedoutTimer < 1 and isDead then
        local JailTime = exports['SickJail']:GetJailTime()
        if JailTime then		
            exports['SickJail']:JailLogin()
        else
            StartRPDeath()
        end
    end
end)
```
{% endtab %}
{% endtabs %}



## Built In Medic System:



{% tabs %}
{% tab title="GetHelp Function ESX Abmulance Job" %}
```lua
function GetHelp()       
    TriggerEvent("esx_ambulancejob:revive") -- put any healing triggers here!
end 
```
{% endtab %}

{% tab title="GetHelp Function Wasabi Abmulance Job" %}
<pre class="language-lua"><code class="lang-lua"><strong> function GetHelp()  
</strong><strong>   TriggerServerEvent('SickJail:dkajsod', GetPlayerServerId(PlayerId()))
</strong>    Citizen.Wait(1000)
end  
</code></pre>

```lua
RegisterServerEvent('SickJail:dkajsod')
AddEventHandler('SickJail:dkajsod', function(id)
    exports.wasabi_ambulance:RevivePlayer(id)
end)
```
{% endtab %}
{% endtabs %}



## Send To Jail

Example of sending players to jail and what is needed!

```lua
local input = lib.inputDialog('Jail Menu', {'Player', 'Time', 'Reason'})  -- Lib Input

if not input then -- if no input then close
    lib.hideContext(false)
    return 
end
local player = tonumber(input[1]) -- Players Server ID (E.X. = 1)
local jailTime = tonumber(input[2]) -- The amount of jail time for the player
local reason = input[3] -- What is the reason/charges for sending to jail
if jailTime <= 0 then -- checks you dont try to put less than zero in the time
    lib.notify({
        title = 'Jail',
        description = 'Jail needs to be Greater than 0 Months!',
        type = 'error'
    })
    return
end
TriggerServerEvent("sickJail:jailPlayer", player, jailTime, reason) -- Server Event for jailing players!
```



{% hint style="info" %}
<pre class="language-lua"><code class="lang-lua"><strong>TriggerServerEvent("sickJail:jailPlayer",player,jailTime,reason) 
</strong><strong>-- Server Event for jailing players!
</strong></code></pre>
{% endhint %}

```
(player) is the players ID you are sending
(jailTime) is the amouunt of time to send the player
(reason) is the reason for being sent. This can be anything and is mainly for Webhooks
```
