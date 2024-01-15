# Events

## T1ger Gangs

T1ger Gangs is now fully supported for many things. Mainly Gang Name check and rank checks! This means instead of using base ESX or QBCore Jobs you can use T1ger Gangs. Players will be able to have a legal job while keeping their gang lives seperate!

Few Things are needed in the `Config` in order for this to fully work!

## SQL

{% hint style="info" %}
The SQL for Trap houses is no longer needed as the script will check the config and if the house is not already created it will create it according to the Configed Gang Names and Configed Key Codes! Example Below
{% endhint %}

```lua
gangName = 'Ballas', -- Gang name linked to T1ger Gangs
code = 6666, -- this is now how its added instead of SQL or messing with your DB!
```



## Config

{% hint style="danger" %}
Make sure you add the T1ger Gang Name to this table&#x20;

`GangName = [Gang Name]`
{% endhint %}

```lua
Config.Gangs = {
    {name = 'police', GangName = 'Police', rank = 0}, -- Police needs to be here if you want them to be able to access Trap Houses. if not simply remove them from the table!
    {name = 'ballas', GangName = 'Ballas', rank = 0}, -- Rank is for keeping lower ranks from changing the KeyCode
    {name = 'families', GangName = 'Families', rank = 0},
    {name = 'vagos', GangName = 'Vagos', rank = 0}
}
```
