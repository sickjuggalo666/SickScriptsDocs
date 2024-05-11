# Installation

Here you will find the different ways to install the script depending on your inventory/framework! These exports will probably be used for a few of my scripts!

{% tabs %}
{% tab title="OX_Inventory" %}
<mark style="color:green;">Nothing is needed to make this work with ox\_inventory. Out of box this is the best way to use the script and will provide the most uses!</mark>
{% endtab %}

{% tab title="QB_Inventory" %}
## <mark style="color:red;">Here we need to add a few exports that are not default in QB Inventory.</mark>&#x20;

{% code title="qb_inventory/server/main" %}
```lua
exports('AddToStash',AddToStash)
exports('RemoveFromStash',RemoveFromStash)
exports('GetStashItems',GetStashItems)
```
{% endcode %}

{% code title="Add item to stash" fullWidth="true" %}
```lua
exports.qb_inventory:AddToStash(stashID, slot, otherslot, itemName, amount, info)
```
{% endcode %}

* <mark style="color:red;">stashID</mark> = the ID of the stash to add the item to
* <mark style="color:red;">slot</mark> = the desired slot
* <mark style="color:red;">otherslot</mark> = the slot that the item is added to if item is not unique
* <mark style="color:red;">itemName</mark> = the item you want to add
* <mark style="color:red;">amount</mark> = the amount you want to add
* <mark style="color:red;">info</mark> = any info/metadata for the item (optional)

{% code title="Remove item from Stash" %}
```lua
exports.qb_inventory:RemoveFromStash(stashId, slot, itemName, amount)
```
{% endcode %}

* <mark style="color:red;">stashId</mark> = the stash ID you want to add the item to
* <mark style="color:red;">slot</mark> = the slot to add the item to (not sure its needed)
* <mark style="color:red;">itemName</mark> = the item to be added
* <mark style="color:red;">amount</mark> = the amount of the item to be added

{% code title="Get Stash Items" %}
```lua
exports.qb_inventory:GetStashItems(stashId)
```
{% endcode %}

* <mark style="color:red;">stashId</mark> = the stash to get the items from
{% endtab %}
{% endtabs %}

