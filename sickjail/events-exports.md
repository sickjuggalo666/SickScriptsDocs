# Events/Exports

## Jail Check Exports

{% tabs %}
{% tab title="In Jail" %}
Used To Check if Currently in Jail

```lua
local inJail = exports['SickJail']:GetJailTime() 
if inJail then 
    print('You are in jail') 
else 
    print('Yay you are NOT in Jail!') 
end
```
{% endtab %}

{% tab title="Send  Back To Jail" %}
Used To Send Player Back to jail if in jail

```lua
local inJail = exports['SickJail']:GetJailTime() 
if inJail then 
    exports['SickJail']:DeathJailLogin() 
else 
    print('Don't send to jail') 
end
```
{% endtab %}
{% endtabs %}

{% hint style="danger" %}
All Exports are **Client Side** only!
{% endhint %}

## Send To Jail Export/Event

### <mark style="color:red;">Export</mark>

{% code title="Send To Jail Export" %}
```lua
exports('SendPlayerToJail',SendPlayerToJail)
```
{% endcode %}

Example Usage

```lua
local player = GetPlayerServerId(CLOSEST_PLAYER)
local time = 5 -- Amount of time for jail
local reason = String -- optional (Defaults to 'MDT Sentence') Mainly for webhooks
exports.SickJail:SendPlayerToJail(player,time,reason or nil)
```

Good for usage in MDTs and other scripts!&#x20;

### <mark style="color:red;">Event</mark>

The Event Usage isn't as recommended but can be used as well. Its the same usage for Client side as the export (Meaning it accepts the same Arguments) but triggers the Server event instead of the Export.&#x20;

{% tabs %}
{% tab title="Client" %}
```lua
TriggerServerEvent("SickJail:jailPlayer", player, jailTime, reason)
```

Example Usage

```lua
local player = GetPlayerServerId(CLOSEST_PLAYER)
local time = 5 -- Amount of time for jail
local reason = String -- optional (Defaults to 'MDT Sentence') Mainly for webhooks
TriggerServerEvent("SickJail:jailPlayer", player, jailTime, reason)
```
{% endtab %}
{% endtabs %}
