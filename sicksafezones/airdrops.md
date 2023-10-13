# AirDrops

A Part of the SafeZones is that with an item you are able to call in AirDrops. Each AirDrop has different LootTables. The Script will pick a random table to allow you to get items from. All Set in Config!

{% code title="AirDrop Options:" lineNumbers="true" %}
```lua
Config.Airdrops = {
    itemNeeded = 'airdrop_flare', -- item needed for AirDrop
    FallSpeed = 10, -- Try modifying this to see how fast You want the Airdrop to go down | Lowering number, means slowing down airdrop fall speed | Default: 10
    DeletePrevious = true, -- Deletes Previous Airdrop if new is spawned
    UseFlareParticles = true,
}
```
{% endcode %}

{% code title="LootTable Info:" lineNumbers="true" %}
```lua
Config.LootTables = {
    [1] = {
        items = { -- Item you get list | Types: 'item', 'weapon', 'account'
            { 'water', 5 },
            { 'bread', 10 },
        }
    },
    [2] = {
        items = {
            { 'WEAPON_PISTOL', 1 },
            { 'WEAPON_APPISTOL', 2 },
            { 'money', 5000 },
        }
    },
    [3] = {
        items = {
            { 'WEAPON_PISTOL', 1 },
        }
    },
    [4] = {
        items = {
            { 'money', 5000 },
        }
    },
    [5] = {
        items = {
            { 'WEAPON_PISTOL', 1 },
        }
    },
}
```
{% endcode %}

