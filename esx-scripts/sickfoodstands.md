# 🌭 SickFoodStands

## Config

The Config contains everything you will ever need to change or add! The options are endless and adding more food stands is as simple as copy paste and the changing of some items!

Three Different Menus are in use:

1. Civilian menu for browsing while waiting to order!
2. Toppings to either just play an anim like you are adding toppings or there is an option to make it give you the item!
3. Cooking menu is locked behind a job and the only reason ESX is currently needed for this script!



## Civilian Menu

Civilian Menu is used for browsing what the shop has to offer! Make sure if you change shop items to add them here as well! Price is just for visual but should be set to what the shops want them sold for!

```lua
menu = {
    coords = vec3(238.1508, -818.6410, 30.1500), --Civilian menu location
    size = vec3(1,1,1), -- Size for BoxZones
    rotation = 90,-- Rotation for BozZones
    label = 'See the Menu', -- target label
    options = {
        {
            title = 'Hot Dog', -- item label
            description = 'Hot off the grill. \n Price: $5', --change price here just visual
            icon = 'hand', -- item icon
            disabled = true, -- this is so you can't click on it
        },
        {
            title = 'Hamburger',
            description = 'No cheese please. \n Price: $5', --change price here just visual
            icon = 'circle',
            disabled = true,
        },
        {
            title = 'CheeseBurger',
            description = 'Yummm Cheese! \n Price: $5', --change price here just visual
            icon = 'bars',
            disabled = true
        }
    }
},
```



## Toppings Menu

Toppings could just be an animation that playes and you RP adding items to your burgers/hotdogs OR you could add items to give!

```lua
ToppingsMenu = {
    coords = vec3(241.8199, -815.2133, 30.0147), -- Coords for Toppings menu
    size = vec3(1,1,1), -- size of BoxZone
    rotation = 90, -- rotation of BoxZone
    label = 'Get Toppings', -- target label
    options = {
        {
            title = 'Ketchup',
            description = 'Everyone loves Ketchup!',
            icon = 'hand',
            args = {
                item = 'ketchup',
                remove = false
            },
            onSelect = function(args)
                lib.hideContext(false)
                if lib.progressCircle({
                    duration = 5000,
                    position = 'bottom',
                    useWhileDead = false,
                    canCancel = true,
                    disable = {
                        car = true,
                        move = true,
                        combat = true
                    },
                    anim = {
                        dict = 'anim@gangops@facility@servers@bodysearch@',
                        clip = 'player_search'
                    }
                }) 
                then 
                    --TriggerServerEvent('SickFoodStands:GetItem',args, 1)-- you could add an item we just thought it was better as just an animation
                else 
                    print('Do stuff when cancelled') 
                end    
            end,
        },
        {
            title = 'Mustard',
            description = 'Some like it some don\'t!',
            icon = 'circle',
            args = {
                item = 'mustard',
                remove = false
                },
            onSelect = function(args)
                lib.hideContext(false)
                if lib.progressCircle({
                    duration = 5000,
                    position = 'bottom',
                    useWhileDead = false,
                    canCancel = true,
                    disable = {
                        car = true,
                        move = true,
                        combat = true
                    },
                    anim = {
                        dict = 'anim@gangops@facility@servers@bodysearch@',
                        clip = 'player_search'
                    }
                }) 
                then 
                    --TriggerServerEvent('SickFoodStands:GetItem',args, 1)-- you could add an item we just thought it was better as just an animation
                else 
                    print('Do stuff when cancelled') 
                end    
            end,
        },
        {
            title = 'Pickle Relish',
            description = 'What Good is a Glizy with out some Reli?',
            icon = 'bars',
            args = {
                item = 'relish',
                remove = false
            },
            onSelect = function(args)
                lib.hideContext(false)
                if lib.progressCircle({
                    duration = 5000,
                    position = 'bottom',
                    useWhileDead = false,
                    canCancel = true,
                    disable = {
                        car = true,
                        move = true,
                        combat = true
                    },
                    anim = {
                        dict = 'anim@gangops@facility@servers@bodysearch@',
                        clip = 'player_search'
                    }
                }) 
                then 
                    --TriggerServerEvent('SickFoodStands:GetItem',args, 1)-- you could add an item we just thought it was better as just an animation
                else 
                    print('Do stuff when cancelled') 
                end    
            end,
        }
    }
}
```



## Cook Menu

Cooking menu is where the shops will make the items to sell! Make sure you look over the options here as there is alot to it!

```lua
coords = vec3(240.3483, -818.4785, 30.4268), --Coords for Cooking menu
size = vec3(1,1,1),
rotation = 90,
job = 'police', -- What job can use this menu?
label = 'Open Cooking',
options = {
    {
        title = 'Hot Dog',
        description = 'Whip up a Glizy',
        icon = 'hand',
        args = {
        item = 'hotdog', --This is the item added make sure its an actual item
        remove = true,
        item1 = 'water',
        item2 = 'hotdog'
        },
        onSelect = function(args)
        lib.hideContext(false)
            local input = lib.inputDialog('Food Stand', {{type = 'number', label = 'Enter Amount', description = 'How Many do you want?', icon = 'hashtag'}})
            if not input or input[1] == '' then return end
            local count = input[1] -- this is the count sent from the input dialog
            if count > 10 then -- you can change max count here
                lib.notify({
                    title = 'Food Stand',
                    description = 'You can\'t take that many!',
                    type = 'error'
                })
                return
            end
            if lib.progressCircle({
                duration = 5000,
                position = 'bottom',
                useWhileDead = false,
                canCancel = true,
                disable = {
                    car = true,
                    move = true,
                    combat = true
                },
                anim = {
                    dict = 'anim@gangops@facility@servers@bodysearch@',
                    clip = 'player_search'
                }
            }) 
            then 
                local inventory1 = exports.ox_inventory:Search('count', 'hotdog') -- stupid af
                local inventory2 = exports.ox_inventory:Search('count', 'water') -- stupid af
                if inventory1 >= count then 
                    if inventory2 >= count then -- but only way to do it
                        TriggerServerEvent('SickFoodStands:GetItem',args, count)-- args.item = item, count = count of how many
                    else
                        lib.notify({
                            title = 'Food Stand',
                            description = 'You need more Buns',
                            type = 'error'
                        })
                    end
                else
                    lib.notify({
                        title = 'Food Stand',
                        description = 'You need more HotDogs',
                        type = 'error'
                    })
                end
            else 
                print('Do stuff when cancelled') 
            end    
        end,
        metadata = {
            {label = 'Item 1', value = 'Hot Dog Bun'}, --metadata for needed items
            {label = 'Item 2', value = 'Hot Dog'}
        },
    },
    {
        title = 'Hamburger',
        description = 'The staple in any daily diet',
        icon = 'circle',
        args = {
        item = 'burger',
        remove = true,
        item1 = 'meat',
        item2 = 'buns'
        },
        onSelect = function(args)
        lib.hideContext(false)
        local input = lib.inputDialog('Food Stand', {{type = 'number', label = 'Enter Amount', description = 'How Many do you want?', icon = 'hashtag'}})
            if not input or input[1] == ' ' then return end
            local count = input[1]
            if count > 10 then
                lib.notify({
                    title = 'Food Stand',
                    description = 'You can\'t take that many!',
                    type = 'error'
                })
                return
            end
            if lib.progressCircle({
                duration = 5000,
                position = 'bottom',
                useWhileDead = false,
                canCancel = true,
                disable = {
                    car = true,
                    move = true,
                    combat = true
                },
                anim = {
                    dict = 'anim@gangops@facility@servers@bodysearch@',
                    clip = 'player_search'
                }
            }) 
            then 
                local inventory1 = exports.ox_inventory:Search('count', 'meat') -- stupid af
                local inventory2 = exports.ox_inventory:Search('count', 'buns') -- stupid af
                if inventory1 >= count then 
                    if inventory2 >= count then -- but only way to do it
                        TriggerServerEvent('SickFoodStands:GetItem',args, count)-- args.item = item, count = count of how many
                    else
                        lib.notify({
                            title = 'Food Stand',
                            description = 'You need more Meat',
                            type = 'error'
                        })
                    end
                else
                    lib.notify({
                        title = 'Food Stand',
                        description = 'You need more Buns',
                        type = 'error'
                    })
                end
            else 
                print('Do stuff when cancelled') 
            end    
        end,
        metadata = {
            {label = 'Item 1', value = 'Hamburger Bun'},
            {label = 'Item 2', value = 'Meat'}
        },
    },
    {
        title = 'CheeseBurger',
        description = 'Yummm Cheese!',
        icon = 'bars',
        args = {
        item = 'cheeseburger',
        remove = true,
        item1 = 'cheese',
        item2 = 'burger'
        },
        onSelect = function(args)
        lib.hideContext(false)
        local input = lib.inputDialog('Food Stand', {{type = 'number', label = 'Enter Amount', description = 'How Many do you want?', icon = 'hashtag'}})
            if not input or input[1] == '' then return end
            local count = input[1]
            if count > 10 then
                lib.notify({
                    title = 'Food Stand',
                    description = 'You can\'t take that many!',
                    type = 'error'
                })
                return
            end
            if lib.progressCircle({
                duration = 5000,
                position = 'bottom',
                useWhileDead = false,
                canCancel = true,
                disable = {
                    car = true,
                    move = true,
                    combat = true
                },
                anim = {
                    dict = 'anim@gangops@facility@servers@bodysearch@',
                    clip = 'player_search'
                }
            }) 
            then 
                TriggerServerEvent('SickFoodStands:GetItem',args, count)
            else 
                print('Do stuff when cancelled') 
            end    
        end,
        metadata = {
            {label = 'Item 1', value = 'Hamburger Bun'},
            {label = 'Item 2', value = 'Hamburger'},
            {label = 'Item 3', value = 'Cheese'},
        },
    }
},
```
