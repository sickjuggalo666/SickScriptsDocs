# Job Info

UpNAtom comes with lots of things to it. Ranging from Drink stations to Friers.



## Job Options

1. Grill to make eggs, pancakes, burgers and more.
2. Frier for Fried Chicken, Fries, Fried Deserts and more.
3. Fridge/Freezer for storing food.
4. Drink Stations with Small, Medium, and Large Sizes.
5. Registers
6. Cleaning
7. Boss Menu



## Drink Station

The Drink station is ran of a Bib system similar to real resturaunts. Each time the drink is used a portion or the supply is removed. Once it is depleted you will no longer be able to sell that type until you refill the supply!

```json
{
    "id": 1,
    "description": "Crispppp",
    "progress": 96,
    "item": "sprite",
    "title": "Sprite",
    "type": "small",
    "icon": "fas-fa-circle"
},
```

{% hint style="danger" %}
Drinks are ran of a JSON to save the progress and to safe on DataBase Calls! Examples are there to help you on making sure you add/remove items correctly!
{% endhint %}



## Registers

Registers are also ran of a JSON file to help make sure that each register is independent when it comes to paying

```json
[
    {
        "currentAmount": 0,
        "name": "register_1"
    },
    {
        "currentAmount": 0,
        "name": "register_2"
    },
    {
        "currentAmount": 0,
        "name": "register_3"
    }
]
```

Accepted Payment Types:

1. Cash
2. Bank



## Friers

The Friers are there to help you make fried chicken for sandwiches and fries for sides. Some Fried Deserts will be included!



## Stove

The Stove will assist in making fresh eggs, cooked burgers, crispy hash browns and buttery pancakes! Each needs an item set in config and has a small skill check after the progress bar, this is to show you actually made it and if you fail the check you will have 'burnt' the item and will have lost it!&#x20;



## Storages

There are 3 pre set storages for the resturaunt to store uncooked meats and buns or fresh cooked meals ready for sale!

{% hint style="info" %}
1. Freezer for Meats and other items
2. Fridge for cheeses, buns, lettuce and more
3. Warmer to place fresh cooked meals in so that the service people can sell the food!
{% endhint %}



## Cleaning

\*\*Coming Soon\*\*
