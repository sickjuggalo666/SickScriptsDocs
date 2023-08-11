# Events

{% hint style="success" %}
Invoices are sent Directly to the Bank
{% endhint %}

Using PEFCL (Project Error Financial) you can send the invoice directly to the bank where you will need to pay it or after the time it will attempt to keep paying it until it is settled!

```lua
Bank:createInvoice(src, {
    to = PlayerName,                        -- {this is PLAYERS name}
    toIdentifier = target.identifier,       -- {the Target Players ID}
    from = OfficerName,                     -- {this is YOUR name}
    fromIdentifier = xPlayer.identifier,    -- {YOUR ID}
    amount = amount,                        -- {Amount sent from Client}
    message = reason,                       --{ Reason Sent from Client}
    receiverAccountIdentifier = xPlayer.identifier {-- if you dont want personal rewards for tickets put this as { Job } and it will send the money to the job not player!}
})
```



{% hint style="success" %}
Tickets are sent to Officer and to an Inventory created to store these!
{% endhint %}

Tickets can be handed over to Player if you choose to do that or kept for records. There is already a Records system built in that will help you keep track of who does what ticket. This helps if you do something like a quota or bonuses for doing more tickets. As long as officer puts their name they will have a good recording.

```lua
local info = {
    amount = amount,
    PlayerName = PlayerName,
    OfficerName = OfficerName,
    date = date
}

if Inventory:CanCarryItem(src, 'ticket', 1) then    -- if officer can carry ticket
    Inventory:AddItem(src, 'ticket', 1, info )      -- add item
else                                                -- else if not can carry
    Inventory:AddItem('police_tickets', 'ticket', 1, info)      -- add item to storage
end

Inventory:AddItem('police_tickets', 'ticket', 1, info)  -- ALWAYS add a copy to storage
```



{% hint style="success" %}
Webhooks are set up for admin to monitor who does what with the tickets. Easier to maintain
{% endhint %}

On Server sided lua there is a part for your WebHook! Server side is also where you can check the invoice to decide if you want pd or the person sending the ticket to get the money. There are notes in there to make sure you understand what is happening there!

```lua
local Discord_url = '' -- server side to protect your webhooks

local function LetEmKnow(message, footer)
    local embed = {
        {
            ["color"] = 3085967,
            ["title"] = "**Sick Ticket System**",
            ["description"] = message,
            ["footer"] = {
                ["text"] = 'New Ticket',
            },
            ["author"] = {
            ["name"] = 'Made by | SickJuggalo666',
            ['icon_url'] = 'https://i.imgur.com/arJnggZ.png'
            }
        }
    }
   PerformHttpRequest(Discord_url, function(err, text, headers) end, 'POST', json.encode({username = "Sick Ticket System", embeds = embed}), { ['Content-Type'] = 'application/json' })
end
```



{% hint style="success" %}
This is where the other copy goes AUTOMATICALLY after creation
{% endhint %}

```lua
Citizen.CreateThread(function()
    for k, v in pairs(Config.Jobs) do
        local tickets = {
            id = v.id,
            label = v.label,
            slots = v.slots,
            maxWeight = v.maxWeight,
            groups = { [v.name] = v.rank }
        }

        Inventory:RegisterStash(tickets.id, tickets.label, tickets.slots, tickets.maxWeight, nil, tickets.groups)
        print(('Creating Inventory for %s, Label: %s, Slots: %s, MaxWeight: %s, Groups: %s'):format(tickets.id,tickets.label,tickets.slots,tickets.maxWeight,tickets.groups))
    end
end)
```



{% tabs %}
{% tab title="Client Notification" %}
```lua
function CNotify(noty_type,message)
    if noty_type and message then
        if Config.Notifications.Client == 'esx' then
            ESX.ShowNotification(message)

        elseif Config.Notifications.Client == 'okok' then
            if noty_type == 1 then
                exports['okokNotify']:Alert('Fines', message, 2500, 'success')
            elseif noty_type == 2 then
                exports['okokNotify']:Alert('Fines', message, 2500, 'info')
            elseif noty_type == 3 then
                exports['okokNotify']:Alert('Fines', message, 2500, 'error')
            end

        elseif Config.Notifications.Client == 'YOUR_NOTIFICATIONS_HERE' then

        end
    end
end
```
{% endtab %}

{% tab title="Server Notification" %}
None Currently!
{% endtab %}
{% endtabs %}
