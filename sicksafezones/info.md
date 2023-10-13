# Info

The Config is pretty simple and easy to use!

{% code lineNumbers="true" %}
```lua
Config = {}
Config.ESX = true -- this is LEGIT ONLY for the airdrop usable item. I could have made it a command but having the item i feel is better. If not i can change!
Config.Notifications = 'ox' -- ox or custom (Change in both Server/Client Utils.lua)
Config.UseZoneMusic = true
-- ### SAFE ZONE INFO

Config.Zones = {
    [1] = {
        name = 'The Lawless Coalition',
        points = {
            vec(741.7549, 169.6226, 85.3060),
            vec(742.7230, 168.8449, 85.3060),
            vec(742.7230, 168.8449, 85.3060),
            vec(753.2601, 157.8367, 85.3060),
            vec(758.5970, 140.8634, 85.3060),
            vec(752.3124, 128.2491, 85.3060),
            vec(730.3325, 96.1845, 85.3060),
            vec(706.8033, 64.4220, 85.3060),
            vec(639.3295, 92.4176, 85.3060),
            vec(677.2900, 196.5964, 85.3060),
        },
        thickness = 10,
        debug = true,
    },
    --[[[2] = {
        name = 'The Lawless Coalition',
        points = {
            vec(1734.9298, 3758.7937, 33.00),
            vec(1688.0013, 3731.7791, 33.00),
            vec(1663.1671, 3774.9126, 33.00),
            vec(1705.8721, 3804.2649, 33.00)
        },
        thickness = 10,
        debug = true,
    }]]
}

Config.MusicInfo = {
    [1] ={
        name = 'safezone1',
        link = 'https://www.youtube.com/watch?v=YUoHI2gDf7k',
        volume = 0.4,
        coords = vector3(696.2985, 130.9088, 83.8779),
        distance = 75
    },
    --[[[2] ={
        name = 'safezone2',
        link = 'https://www.youtube.com/watch?v=d_uqlELD4qw',
        volume = 0.3,
        coords = vector3(1699.2564, 3771.0712, 34.524211),
        distance = 37
    },]]
}

Config.BlackList = {
    [1] = {
        name = 'WEAPON_MINISMG'
    },
    [2] = {
        name = 'WEAPON_ASSAULTRIFLE'
    },
    [3] = {
        name = 'WEAPON_APPISTOL'
    },
    [4] = {
        name = 'WEAPON_PISTOL'
    }
}


-- ### AIR DROP INFO
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

Config.Airdrops = {
    itemNeeded = 'airdrop_flare',
    FallSpeed = 10, -- Try modifying this to see how fast You want the Airdrop to go down | Lowering number, means slowing down airdrop fall speed | Default: 1
    DeletePrevious = true, -- Deletes Previous Airdrop if new is spawned
    UseFlareParticles = true,
}

-- ### SCRAP CAR LOOT INFO

Config.Cars = {
    [1] = {
        hash = `prop_rub_carwreck_9`,
        lootTable = 'prop_rub_carwreck_9',
        name = 'car',
        icon = 'fa-solid fa-capsule',
        label = 'Search',
        items = 'lockpick', -- or items = {lockpick = 1, hacing_device = 1} if they have one it will work
    }
}

Config.CarLoot = {
    ['prop_rub_carwreck_9'] = {
        items = { -- Item you get list | Types: 'item', 'weapon', 'account'
            { 'water', 5 },
            { 'bread', 10 },
        }
    }
}
```
{% endcode %}
