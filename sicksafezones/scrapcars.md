# ScrapCars

A New Part to this script is being able to search random scrap cars around the map. Each with their own LootTable that you can adjust anyway you want! A Cool feature is that once a car is searched its not searchable again until the script has restarted or a server restart happened! The cars can also be locked behind an item of your choosing. This means in order for the Option to show for searching they must have atleast on of the items. You can change add remove or do whatever you want with this part!

{% code title="ScrapCar Options:" lineNumbers="true" %}
```lua
Config.Cars = {
    [1] = {
        hash = `prop_rub_carwreck_9`, -- What model?
        lootTable = 'prop_rub_carwreck_9', -- LootTable for Config.CarLoot
        name = 'car', -- name of the target can change if you want
        icon = 'fa-solid fa-capsule', -- icon for target https://fontawesome.com/
        label = 'Search', -- label if you choose to change it
        items = 'lockpick', -- or items = {lockpick = 1, hacing_device = 1} if they have one it will work
    }
}
```
{% endcode %}

{% code title="CarLoot:" lineNumbers="true" %}
```lua
Config.CarLoot = {
    ['prop_rub_carwreck_9'] = { -- must match lootTable in Config.Cars
        items = { -- Item you get list | Types: 'item', 'weapon', 'account'
            { 'water', 5 },
            { 'bread', 10 },
        }
    }
}
```
{% endcode %}
