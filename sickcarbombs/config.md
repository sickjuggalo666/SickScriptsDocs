# Config

## SmartFires

Added Support for SmartFires. Uses exports to start a fire at the location of the explosion. If you choose to use this option set the Config option to `true`

```lua
Config.SmartFires = true -- to start fires at explosions
```

## Speed

```lua
Config.Speed = 'MPH' -- 'MPH' or 'KPH'
```

## Items

If you choose to change the items used this can be done in the config!

{% code title="Config.IEDItem" lineNumbers="true" %}
```lua
Config.IEDItem = {
    timer = 'ied_timer',
    speed = 'ied_speed',
    seat = 'ied_delayed',
    instant = 'ied_instant',
    remote = 'ied_remote'
}
```
{% endcode %}

## Remote Detonation Options

{% code lineNumbers="true" %}
```lua
Config.TriggerKey = 47 -- for remote bombs
Config.TriggerKeyLabel = 'G' -- label for textUI
```
{% endcode %}

## Notifications

{% code lineNumbers="true" %}
```lua
function CNotify(type,message) -- can change to any if you want
    if type == 1 then -- 3 types, (1,2,3)
        lib.notify({
            title = 'Car Bomb', -- title for notifications
            description = message, -- Message comes from locals file
            type = 'success' -- type goes with type
        })
    elseif type == 2 then
        lib.notify({
            title = 'Car Bomb',
            description = message,
            type = 'inform'
        })
    elseif type == 3 then
        lib.notify({
            title = 'Car Bomb',
            description = message,
            type = 'error'
        })
    end
end
```
{% endcode %}
