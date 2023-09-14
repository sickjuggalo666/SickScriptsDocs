# Items

To get started we just need to add a few items to our DB or if using Ox\_Inventory put them in your items.lua! Below are the needed items for this to work:

<pre class="language-sql" data-title="Database SQL" data-line-numbers><code class="lang-sql"><strong>INSERT INTO `items` (`name`, `label`, `weight`, `rare`, `can_remove`) VALUES 
</strong>    ('ied_timer', 'Timer Explosive Device', 1, 0, 1),
    ('ied_speed', 'Speed Explosive Device', 1, 0, 1),
    ('ied_remote', 'Remote Explosive Device', 1, 0, 1),
    ('ied_delayed', 'Delayed Explosive Device', 1, 0, 1),
    ('ied_instant', 'Instant Explosive Device', 1, 0, 1),
;
</code></pre>

{% code title="ox_inventory/data/items.lua" lineNumbers="true" %}
```lua
['ied_timer'] = {
    label = 'Timer IED',
    weight = 1,
    stack = true,
    close = true,
},

['ied_speed'] = {
    label = 'Speed IED',
    weight = 1,
    stack = true,
    close = true,
},

['ied_remote'] = {
    label = 'Remote IED',
    weight = 1,
    stack = true,
    close = true,
},

['ied_delayed'] = {
    label = 'Delayed IED',
    weight = 1,
    stack = true,
    close = true,
},

['ied_instant'] = {
    label = 'Instant IED',
    weight = 1,
    stack = true,
    close = true,
},
```
{% endcode %}

