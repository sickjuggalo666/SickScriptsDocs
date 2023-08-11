# General info



## Config

```lua
Config = {}

Config.OrderTimer = 280
Config.ShopAccount = 'money' -- bank, money, black_money
Config.BlipCoords = {
    {
        BlipName = "Up n\' Atom", 
        BlipID = 269, 
        BlipScale = 1.0, 
        x = 85.9631,
        y = 284.8619, 
        z = 110.6538, 
        BlipColor = 49
    },
}

Config.JobPickUp = {
    coords = vector3(2434.5593, 5011.3726, 46.8275),
    blipData = {
        enable = true,
        label = 'Food Pickup',
        sprite = 280,
        display = 4,
        scale = 0.8,
        color = 5,
        route = true
    }
}

Config.Notifications = {
    client = 'ox',
    server = 'ox'
}

Config.Veh = {
    [1] = {
        model = 'rumpo',
        coords = {x = 121.8951, y = 297.4249, z = 109.7900},
        heading = 159.2774
    }
}

Config.Registers = {
    [1] = {
        name = 'register_1',
        coords = vector3(89.7878, 287.7055, 110.2055),
        size = vec3(1, 2, 3),
        rotation = 30,
        debug = false,
        icon = 'fas-fa-burger',
        label = 'Open Register!',
    }
}

Config.DrinkStation = {
    [1] = {
        name = 'drinkStation_1',
        coords = vector3(93.3012, 286.8039, 110.2094),
        size = vec3(1, 2, 3),
        rotation = 30,
        debug = false,
        icon = 'fas-fa-burger',
        label = 'Grab a Fresh Drink!',
    }
}

Config.Fries = {
    [1] = {
        name = 'fries_1',
        coords = vector3(92.1997, 292.0820, 110.2094),
        size = vec3(1, 2, 3),
        rotation = 30,
        debug = false,
        name = 'atom_frier',
        icon = 'fas-fa-burger',
        label = 'Cook Up Some Fries!',
        name2 = 'chicken_frier',
        icon2 = 'fas-fa-burger',
        label2 = 'Make Fried Chicken!',
    }
}

Config.Stoves = {
    [1] = {
        name = 'stove_1',
        coords = vector3(94.6233, 291.7034, 110.2094),
        size = vec3(1, 2, 3),
        rotation = 30,
        debug = false,
        icon = 'fas-fa-burger',
        label = 'Cook Up Some Food!',
    }
}

Config.Storages = {
    [1] = {
        name = 'fridge',
        coords = vector3(94.5751, 288.7962, 110.2094),
        size = vec3(1, 2, 3),
        rotation = 30,
        debug = false,
        icon = 'fas-fa-burger',
        label = 'Open Fridge!',
        id = 'atom_fridge',
        label = 'Up n\' Atom Fridge',
        slots = 50,
        weight = 100000,
    },
    [2] = {
        name = 'deep_freeze',
        coords = vector3(89.0101, 292.5507, 110.2095),
        size = vec3(1, 2, 3),
        rotation = 30,
        debug = false,
        icon = 'fas-fa-burger',
        label = 'Open Freezer!',
        id = 'atom_freezer',
        label = 'Up n\' Atom Freezer',
        slots = 50,
        weight = 100000,
    },
    [3] = {
        name = 'foodWarmer_1',
        coords = vector3(91.1882, 288.3933, 110.2094),
        size = vec3(1, 2, 3),
        rotation = 30,
        debug = false,
        icon = 'fas-fa-burger',
        label = 'Open Warmer!',
        id = 'atom_warmer',
        label = 'Up n\' Atom Warmer',
        slots = 15,
        weight = 50000,
    }
}

Config.BossMenu = {
    [1] = {
        job = 'upnatom', -- this job not only allows access to BossMenu but is the job read by script
        rank = 2,
        coords = vector3(81.5861, 296.2689, 110.2495),
        size = vec3(1, 2, 3),
        rotation = 30,
        debug = false,
        name = 'atom_boss_menu',
        icon = 'fas-fa-burger',
        label = 'Open Boss Menu!',
        name2 = 'atom_order_menu',
        icon2 = 'fas-fa-burger',
        label2 = 'Place An Order',
    }
}

Config.Menu = {
    [1] = {
        item = 'cooked_burger',
        title = 'Cooked Burger',
        description = 'Make a fresh meat patty',
        icon = 'circle',
        itemNeeded = 'meat',
        items = { 
            {
                item = 'meat', 
                amount = 1 
            }
        }
    },
    [2] = {
        item = 'footlong_chiliDog',
        title = 'HotDog',
        description = 'Make a Hot Dog',
        icon = 'circle',
        items = {            
            {
                item = 'hotdog', 
                amount = 1 
            }
        }
    },
    [3] = {
        item = 'fried_egg',
        title = 'Fried Egg',
        description = 'Make a Fried Egg',
        icon = 'circle',
        items = {            
            {
                item = 'egg', 
                amount = 1 
            }
        }
    },
    [4] = {
        item = 'pancakes',
        title = 'Pancakes',
        description = 'Make Some Buttery Pancakes',
        icon = 'circle',
        items = {            
            {
                item = 'pancakes', 
                amount = 1 
            }
        }
    },
    [5] = {
        item = 'eggs_benidict',
        title = 'Eggs Benidict',
        description = 'Make Eggs Benidict',
        icon = 'circle',
        items = {            
            {
                item = 'eggs', 
                amount = 1 
            }
        }
    }
}

Config.Shop = {
    [1] = {
        item = 'meat',
        title = 'Uncooked Meat',
        description = 'Get Uncooked Meat',
        icon = 'circle',
        price = 10
    },
    [2] = {
        item = 'hotdog',
        title = 'HotDogs',
        description = 'Get Fresh HotDogs From the Farm!',
        icon = 'circle',
        price = 10
    },
    [3] = {
        item = 'eggs',
        title = 'Fresh Eggs',
        description = 'Nothing Fresher than these!',
        icon = 'egg',
        price = 10
    },
    [4] = {
        item = 'bacon',
        title = 'Uncooked Bacon',
        description = 'Mmmm that smell!',
        icon = 'circle',
        price = 10
    }
}
```



## Inventories

{% hint style="info" %}
Inventories are automatically built first time the script is started. The Script will print if it is creating the inventories then each time script is started it checks those inventories and if they already exist does nothing!
{% endhint %}

