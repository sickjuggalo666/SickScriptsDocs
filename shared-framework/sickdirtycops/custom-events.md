# Custom Events

Adding your own custom events/triggers into Dirty Cops Is SUPER easy. Below I will show you step by step how to add a Function and target option!

## Target Option:

{% code title="client/Cutils.lua" lineNumbers="true" %}
```lua
{
  name = 'ox:option9',
  icon = 'fa-solid fa-money-bill',
  label = 'Test Function',
  canInteract = function(entity, distance, coords, name, bone)
  if distance < 2 then
       return true
  else
       return false
  end
end,
   onSelect = function()
      TestFunction() -- 'YOUR TEST FUNCTION' 
   end
 }
```
{% endcode %}

## Adding the Function:

{% code title="client/Cutils.lua" lineNumbers="true" %}
```stylus
function TestFunction()
    -- Do anything you want here
end
```
{% endcode %}
