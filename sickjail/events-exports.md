# Events/Exports



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
