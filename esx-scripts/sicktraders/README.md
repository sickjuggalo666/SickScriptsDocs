# 🧑💼 SickTraders

## Config

```lua
Config.Zones = {
    ['TrillianChemicalContainment'] = {
        label = 'Trillian Chemical Containment',
        blipCoords = vector3(695.58105, 135.68014, 83.877861),
        BlipSpirte = 770,
        BlipColor = 4,
        BlipSize = 0.7,
        BlipLabel = "Trillian Chemical Containment",
        coords = {
            [1]= {
                UsePed = true, -- Do you want to use a ped?
                coords = vector3(695.60876, 133.03575, 79.960525),
                h = 191.94412,
                size = vec3(3, 2, 3), -- size of the box zone
                rotation = 90, -- Rotation of box zone
                TargetLabel = 'Arms Dealer', -- easier to label for each faction
                ped = 's_m_m_armoured_01',
                menu = 'weapons' -- weapons, med, or food
            },
            [2]= {
                UsePed = true, -- Do you want to use a ped?
                coords = vector3(660.3627, 105.0548, 79.7542),
                h = 348.7023,
                size = vec3(3, 2, 3), -- size of the box zone
                rotation = 90, -- Rotation of box zone
                TargetLabel = 'Chef', -- easier to label for each faction
                ped = 'CSB_Chef',
                menu = 'food'
            },
            [3]= {
                UsePed = true, -- Do you want to use a ped?
                coords = vector3(723.7529, 151.4593, 79.7542),
                h = 150.1906,
                size = vec3(3, 2, 3), -- size of the box zone
                rotation = 90, -- Rotation of box zone
                TargetLabel = 'Dr. FeelGood', -- easier to label for each faction
                ped = 'S_M_M_Doctor_01',
                menu = 'med'
            }
        }, 
        Weaponmenu = {
            {
                title = 'Weapon Pistol',
                description = 'A new Pistol To kill the Zombies!',
                icon = 'gun',
                iconColor = 'red',
                args = {
                    weapon = 'WEAPON_PISTOL',
                    price = 5000,
                    ammo = 'ammo-9', -- (or false if not giving ammo)
                    ammoAmount = 50,
                    shop = 'Trillian Chemical Containment',
                },
                onSelect = function(args)
                    TriggerServerEvent('SickTraders:trade', args)
                end,
                metadata = {
                    {label = 'Price', value = '$5000'},
                    {label = 'Ammo', value = 'x50 Rounds'},
                }
            },
        },
        Foodmenu = {
            {
                title = 'Burger',
                description = 'A Juicy Burger',
                icon = 'gun',
                iconColor = 'red',
                args = {
                    food = 'burger',
                    price = 5,
                    amount = 1,
                },
                onSelect = function(args)
                    TriggerServerEvent('SickTraders:tradeFood', args)
                end,
                metadata = {
                    {label = 'Price', value = '$5'},
                }
            },
        },
        Medmenu = {
            {
                title = 'Tylenol',
                description = 'Won\'t do much againt the virus but will kill them pesky back aches',
                icon = 'pill',
                iconColor = 'red',
                args = {
                    med = 'tylenol',
                    price = 500,
                    amount = 1,
                },
                onSelect = function(args)
                    TriggerServerEvent('SickTraders:Medtrade', args)
                end,
                metadata = {
                    {label = 'Price', value = '$500'},
                }
            },
        }
    },
}
```
