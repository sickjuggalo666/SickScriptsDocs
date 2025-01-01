# Config

{% hint style="danger" %}
The Config has changed slightly with new options and changes to the way other options used to work.&#x20;
{% endhint %}

{% code lineNumbers="true" %}
```lua
Config = {}

Config.Framework = 'ESX' -- 'ESX' or 'QBCore'

Config.Target = 'ox_target' -- 'ox_target', 'qb-target'

Config.SickDirtyCopsHeist = true -- COMING SOON

Config.inventory = 'ox' -- 'ox' / 'qb'

Config.location = {
    {
        UsePed = true, -- Do you want to use a ped?
        coords = vector3(465.6510, -998.3225, 23.9148),
        h = 95.5823,
        size = vec3(3, 2, 3), -- size of the box zone
        rotation = 90, -- Rotation of box zone
        cop = true,  -- is this a police job? allows evidence lockers
        job = {['police'] = 0, ['ambulance'] = 0 }, -- Jobs now are accessable by more than one job and the chief options are only available for the rank with the job
        TargetLabel = 'Open Evidence', -- easier to label for each job
        ped = 's_m_m_armoured_01' -- ped is now location/job based
    },
    {
        UsePed = true,
        coords = vector3(335.5984, -570.5597, 43.2493),
        h = 60.4760,
        job = {['ambulance'] = 0},
        cop = false,
        TargetLabel = 'Open Ambulance Lockers',
        ped = 'S_M_M_Doctor_01'
    }, 
    {
        UsePed = true,
        coords = vector3(-214.3525, -1365.2156, 30.2748),
        h = 159.3064,
        job = {['mechanic'] = 0},
        cop = false,
        TargetLabel = 'Open Mechanic Lockers',
        ped = 'S_M_Y_XMech_02_MP'
    }
}

Config.NotificationType = {
    client = 'ox_libs'
}
```
{% endcode %}

## Inventories

Ox is the main supported inventory but for QBCore users the option to use QB-Inventory is there.&#x20;

```lua
Config.inventory = 'ox' -- 'ox' / 'qb'
```

## Job Config

{% hint style="danger" %}
The old rank and job system has been redone to make for a smoother use and allowing for other jobs to access the same inventories!

There is a difference between <mark style="color:red;">`job`</mark> and <mark style="color:red;">`targetJobs`</mark>
{% endhint %}

{% tabs %}
{% tab title="Target Jobs" %}
```css
targetJobs = {['police'] = 0, ['ambulance'] = 0 }
```

Target Jobs are the jobs that have access to the target options to open the menus. If rank is not above the number set they will not be able to open the menu. Otherwise they will have same access as normal but if it is a Cop job then they will be able to see the evidence portion as well!
{% endtab %}

{% tab title="Job Access" %}
```css
job = {['police'] = 0, ['ambulance'] = 0 }
```

These are the jobs that can open the menu. The corresponding number is for the rank of the Chief options. Any rank above the set number will have access to the Chief options. This is also for any extra job that you put in.
{% endtab %}
{% endtabs %}
