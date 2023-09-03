---
layout:
  title:
    visible: true
  description:
    visible: false
  tableOfContents:
    visible: true
  outline:
    visible: true
  pagination:
    visible: true
---

# Buy/Sell Shop

{% tabs %}
{% tab title="Sell Shop" %}
{% code lineNumbers="true" %}
```lua
Config.SellShops = {
    {
        item = 'emerald',
        label = 'Emerald',
        price = math.random(100,175),
        currency = 'money'
    },
    --[[{
        item = 'diamond',
        label = 'Diamond',
        price = math.random(400,800),
        currency = 'money'
    },]]

}


item = string, 
label = string, 
price = number, 
currency = string
```
{% endcode %}
{% endtab %}

{% tab title="Buy Shop" %}
{% code lineNumbers="true" %}
```lua
Config.BuyShop = {
    {
        item = 'thermite',
        label = 'Thermite',
        price = 10,
        currency = 'money',
        maxAmount = 10
    },
    {
        item = 'c4',
        label = 'C4',
        price = 20,
        currency = 'money',
        maxAmount = 10
    },
}

item = string, 
label = string, 
price = number, 
currency = string,
maxAmount = number
```
{% endcode %}
{% endtab %}
{% endtabs %}

{% hint style="info" %}
```lua
Examples = {
    item = 'c4', -- This will be the item you are buying/selling 
    label = 'Cool Custom Label For the C4', -- Label if you choose to put a different name
    price = 210,  -- price for the item above
    currency = 'black_money', -- can be { 'bank', 'money', 'black_money' }
    maxAmount = 10 -- maxAmount that can be bought each storm
}
```
{% endhint %}

