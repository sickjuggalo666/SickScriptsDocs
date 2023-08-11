# Stashes

Inside the Prison are **THREE** Hidden stashes. These stashes can be used to store items for later Prison Sentences!



{% hint style="danger" %}
Be Careful as other inmates can find these stashes and possibly take your items! The Risk of being in prison!
{% endhint %}

```lua
local stash1 = {
    id = 'jailStash1',        
    invLabel = "Jail Stash",                 
    invWeight = 1000.0,                            
    invSlots = 10                    
}
Inventory:RegisterStash(stash1.id, stash1.invLabel, stash1.invSlots, stash1.invWeight, nil, false)

local stash2 = {
    id = 'jailStash2',        
    invLabel = "Jail Stash",                 
    invWeight = 1000.0,                            
    invSlots = 10                    
}
Inventory:RegisterStash(stash2.id, stash2.invLabel, stash2.invSlots, stash2.invWeight, nil, false)

local stash3 = {
    id = 'jailStash3',        
    invLabel = "Jail Stash",                 
    invWeight = 1000.0,                            
    invSlots = 10                    
}
Inventory:RegisterStash(stash3.id, stash3.invLabel, stash3.invSlots, stash3.invWeight, nil, false)
```
