# Prison Break

Built into SickJail is a prison break system. You will need a Configed Item in order to play one of the Configed Mini games before you are tped out of the prison to a random location!

Working on more to the break out!

```lua
{
    Codesign Keymaster: ['cd_keymaster'], 
    mHacking: ['mHacking'], -- support for these will be limited
    Modfreaks lockpick v1: ['lockpick'], -- support for these will be limited
    ModFreaks Lockpick v2: ['lockpickV2'] -- support for these will be limited
}
```

{% hint style="warning" %}
Will Add more as we come across more or if you have ideas let me know!
{% endhint %}

## Notifications

Built in Police notifications with Codesign Dispatch support out of box!

Built in Webhooks also allow your police/server owners keep track of who has been sent for how long!

```lua
local Discord_url = '' -- Put Discord URL Here!
SendToDiscord = function(color, name, message, footer)
    local embed = {
          {
              ["color"] = 3085967,
              ["title"] = "**".. name .."**",
              ["description"] = message,
              ["footer"] = {
                  ["text"] = 'Made by | SickJuggalo666',
              },
              ["author"] = {
                ["name"] = 'Jail Warden',
                ['icon_url'] = 'https://i.imgur.com/arJnggZ.png'
              }
          }
      }
  
    PerformHttpRequest(Discord_url, function(err, text, headers) end, 'POST', json.encode({username = name, embeds = embed}), { ['Content-Type'] = 'application/json' })
end
```

```lua
function PrisonEscape()
    local data = exports['cd_dispatch']:GetPlayerInfo()
    TriggerServerEvent('cd_dispatch:AddNotification', {
        job_table = {'police', }, 
        coords = data.coords,
        title = '10-99 - Prison Break',
        message = 'A '..data.sex..' Was reported by Warden to be unaccounted for!', 
        flash = 1,
        unique_id = data.unique_id,
        sound = 1,
        blip = {
            sprite = 431, 
            scale = 1.2, 
            colour = 3,
            flashes = true, 
            text = '911 - Prison Break',
            time = 5,
            radius = 0,
        }
    })
    --TriggerServerEvent('sickJail:PoliceNotifySV') -- server side police notify
end
```

