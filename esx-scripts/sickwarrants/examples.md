# Examples

## Config

```lua
Config = {}

Config.CheckVersion = true -- do you wanna stay up to date? will print in server console

Config.MenuType = 'ox_libs'


Config.jobsAuth = {
    ['police'] = true,
    ['bcso'] = true,
}

Config.BountyJobs = {
      ['bondsman'] = true,
      ['police'] = true
}

Config.NotificationType = { --['okokNotify' / 'mythic' / 'esx' / 'chat' / 'custom' ]
    client = 'okokNotify', 
    server = 'okokNotify'
}
```



## Notifications



{% tabs %}
{% tab title="Client" %}
```lua
function Cnotify(noty_type, message)
    if noty_type and message then
        if Config.NotificationType.client == 'esx' then
            ESX.ShowNotification(message)
        elseif Config.NotificationType.client == 'okokNotify' then
            if noty_type == 1 then
                exports['okokNotify']:Alert("Warrants", message, 10000, 'success')
            elseif noty_type == 2 then
                exports['okokNotify']:Alert("Warrants", message, 10000, 'info')
            elseif noty_type == 3 then
                exports['okokNotify']:Alert("Warrants", message, 10000, 'error')
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

{% tab title="Server" %}
```lua
function Snotify(source, noty_type, message) -- Not Needed as is but maybe future update
    if source and noty_type and message then
        if Config.NotificationType.server == 'esx' then
            TriggerClientEvent('esx:showNotification', source, message)        
        elseif Config.NotificationType.server == 'okokNotify' then
            if noty_type == 1 then
                TriggerClientEvent('okokNotify:Alert', source, 'Warrants', message, 10000, 'success')
            elseif noty_type == 2 then
                TriggerClientEvent('okokNotify:Alert', source, 'Warrants', message, 10000, 'info')
            elseif noty_type == 3 then
                TriggerClientEvent('okokNotify:Alert', source, 'Warrants', message, 10000, 'error')
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
