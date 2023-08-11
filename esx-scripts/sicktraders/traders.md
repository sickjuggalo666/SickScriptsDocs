# Traders

## New Traders

{% hint style="danger" %}
When Adding new traders to the config there is an important step to do before you are ready to use the trader system!
{% endhint %}

```lua
if Zone == 'TrillianChemicalContainment' then -- (When creating new traders in the config make sure 
    local Cfg = Config.Zones[Zone] -- this zone MATHCES the configed zone's name!)
    if menu == 'weapons' then -- weapons, food, med or if you add a custom menu
        lib.registerContext({
            id = 'weapons'..Zone,
            title = Cfg.label,
            options = Cfg.Weaponmenu
        })
        lib.showContext('weapons'..Zone)
    elseif menu == 'food' then
        lib.registerContext({
            id = 'food'..Zone,
            title = Cfg.label,
            options = Cfg.Foodmenu
        })
        lib.showContext('food'..Zone)
    elseif menu == 'med' then
        lib.registerContext({
            id = 'med'..Zone,
            title = Cfg.label,
            options = Cfg.Medmenu
        })
        lib.showContext('med'..Zone)

    --[[elseif menu == 'CUSTOM' then -- Example for adding more make sure menu matches a menu in config otherwise it will not open
        lib.registerContext({
            id = 'CUSTOM'..Zone,
            title = Cfg.label,
            options = Cfg.CUSTOMmenu
        })
        lib.showContext('CUSTOM'..Zone)]]
    end
end
```
