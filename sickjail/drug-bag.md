# Drug Bag

Drug Bag is a useful item for while you are in prison and trying to smuggle stuff out! You Can not only open and fill your Drug Bags your are also able to toss them over the fence and use Target to open and destroy the bag! Has minimal slots and minimal weight to prevent lots of items in the drug bags or items that dont seem to "fit"!

```lua
local DrugBag = {
    id = 'drug_bag: '..name,          
    invLabel = "Drug Baggie",                 
    invWeight = 500.0,                            
    invSlots = 5,                 
}
Inventory:RegisterStash(DrugBag.id, DrugBag.invLabel, DrugBag.invSlots, DrugBag.invWeight, false)
```

These will be available from the Gangs! Probably on a higher Rep Level too
