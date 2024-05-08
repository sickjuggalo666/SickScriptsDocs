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



## Adding New Items

```lua
[1] = {
    name = 'weed', -- item name
    amount = 1, -- how many at one time you want sold?
    moneyName = 'black_money',  -- you can put any ITEM here!!! money / black_money for cash
    moneyAmount = math.random(100,300),  -- Equation = { amount * moneyAmount = TotalAmount} E.X = { 1 * 100 = 100 }, { 2 * 100 = 200 }
},
```



* Name = The Name of the input item (item to be exchanged)
* amount = The amount of the above item to be removed
* moneyName = any thing can be your money item or ANY item!! this is the item given in exchange for the above item!
* moneyAmount = The amount of the 'moneyName' to give! math.random DO work here!

