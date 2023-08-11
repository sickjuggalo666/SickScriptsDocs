# Config

```lua
Config = {}

Config.MenuType = 'ox_libs'

Config.Price = 5000 -- price for checking cops AND making inventory
Config.TruckPrice = 5000 -- price to check info on the truck heist
Config.Inventory = 'ox'
Config.Target = 'ox_target'
Config.TruckUSB = 'greenusb'
Config.PoliceJobName = {
    'police'
}
Config.CashAccount = 'black_money'
Config.TruckAccount = 'black_money'
Config.NotificationType = { --['okokNotify' / 'mythic' / 'esx' / 'chat' / 'custom' ]
    client = 'okokNotify', 
    server = 'okokNotify'
}

Config.GreenDongle = 'greenusb' -- item needed to open the Menu

Config.InventoryOptions = { 
    inventoryType = "inventory",
    inventorySubType = "housing",
    inventoryLabel = "drop_box",
    maxWeight = 100.0,
    maxSlots = 10,
    OxLabel = "Drop Box" -- If using ox inventory this matters if not its nothing
}

Config.Peds = {
    [1] = {
        Name = "Zeus Almighty",
        TargetName = 'illegal_shop1',
        SpawnName = 'IG_RoccoPelosi',
        OpenTime = 1, -- Open Time
        CloseTime = 8, -- Closing Time
    },
}

Config.Locations = { -- NEW option for random locations!
    [1] = {
        coords = vector3(-1042.5310, -828.3828, 9.8815),
        h = 127.6541,
    },
    [2] = {      
        coords = vector3(-1033.1675, -836.6893, 9.8819),
        h = 141.4699,
    }
}

Config.TruckInfo = {
    TruckPrice = 5000,
    TruckLocation = vector3(569.46, -3127.42, 18.77)
}

Config.RobberyList = {
    [1] = {
        Header = "Fleeca Banks",
        icon = 'fa-solid fa-bank',
        minCops = 0,
        bank = true,
    },
    [2] = {
        Header = "Store robbery",
        icon = 'fa-solid fa-store',
        minCops = 0,
        bank = false, -- some just need to be here to help script function without error
    },
    [3] = {
        Header = "Pacific Bank",
        icon = 'fa-solid fa-bank',
        minCops = 0,
        bank = true,
    },
    [4] = {
        Header = "House Robbery",
        icon = 'fa-solid fa-house',
        minCops = 0,
        bank = false, -- some just need to be here to help script function without error
    },
    [5] = {
        Header = "Truck Heist",
        icon = 'fa-solid fa-truck',
        minCops = 0,
        bank = false,
    },
}
```



## Notifications

{% tabs %}
{% tab title="Client Notifications" %}
```lua
function Cnotify(noty_type, message)
    if noty_type and message then
        if Config.NotificationType.client == 'esx' then
            ESX.ShowNotification(message)
        elseif Config.NotificationType.client == 'okokNotify' then
            if noty_type == 1 then
                exports['okokNotify']:Alert("Dongle", message, 10000, 'success')
            elseif noty_type == 2 then
                exports['okokNotify']:Alert("Dongle", message, 10000, 'info')
            elseif noty_type == 3 then
                exports['okokNotify']:Alert("Dongle", message, 10000, 'error')
            end
        elseif Config.NotificationType.client == 'mythic' then
            if noty_type == 1 then
                exports['mythic_notify']:SendAlert('success', message, { ['background-color'] = '#ffffff', ['color'] = '#000000' })
            elseif noty_type == 2 then
                exports['mythic_notify']:SendAlert('inform', message, { ['background-color'] = '#ffffff', ['color'] = '#000000' })
            elseif noty_type == 3 then
                exports['mythic_notify']:SendAlert('error', message, { ['background-color'] = '#ffffff', ['color'] = '#000000' })
            end
        elseif Config.NotificationType.client == 'chat' then
            TriggerEvent('chatMessage', message)        
        elseif Config.NotificationType.client == 'other' then
            --add your own notification.       
        end
    end
end
```
{% endtab %}

{% tab title="Server Notifications" %}
```lua
function Snotify(source, noty_type, message) -- Not Needed as is but maybe future update
    if source and noty_type and message then
        if Config.NotificationType.server == 'esx' then
            TriggerClientEvent('esx:showNotification', source, message)        
        elseif Config.NotificationType.server == 'okokNotify' then
            if noty_type == 1 then
                TriggerClientEvent('okokNotify:Alert', source, 'Dongle', message, 10000, 'success')
            elseif noty_type == 2 then
                TriggerClientEvent('okokNotify:Alert', source, 'Dongle', message, 10000, 'info')
            elseif noty_type == 3 then
                TriggerClientEvent('okokNotify:Alert', source, 'Dongle', message, 10000, 'error')
            end
        elseif Config.NotificationType.server == 'mythic' then
            if noty_type == 1 then
                TriggerClientEvent('mythic_notify:client:SendAlert', source, { type = 'success', text = message, style = { ['background-color'] = '#ffffff', ['color'] = '#000000' } })
            elseif noty_type == 2 then
                TriggerClientEvent('mythic_notify:client:SendAlert', source, { type = 'inform', text = message, style = { ['background-color'] = '#ffffff', ['color'] = '#000000' } })
            elseif noty_type == 3 then
                TriggerClientEvent('mythic_notify:client:SendAlert', source, { type = 'error', text = message, style = { ['background-color'] = '#ffffff', ['color'] = '#000000' } })
            end
        elseif Config.NotificationType.server == 'other' then
            --add your own notification.
        end
    end
end
```
{% endtab %}
{% endtabs %}



## Events/Exports



{% hint style="info" %}
These Events can be triggered to set the Robbery Status of Banks that will show in the menu letting Players know if the bank is ready to be robbed or not!
{% endhint %}

{% tabs %}
{% tab title="Server Event" %}
{% code overflow="wrap" %}
```lua
TriggerClientEvent('dongle:UpdateRobberyChecks', source, BOOLEN) --BOOLEN = (true or false)
```
{% endcode %}
{% endtab %}

{% tab title="Client Event" %}
{% code overflow="wrap" %}
```lua
TriggerEvent('dongle:UpdateRobberyChecks', BOOLEN) --BOOLEN = (true or false)
```
{% endcode %}
{% endtab %}
{% endtabs %}

