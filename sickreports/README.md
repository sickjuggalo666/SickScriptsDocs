# 📄 SickReports

Welcome to SickReports. A Simple System for Admins and players to use to help keep track of bugs/players and other general info. Everything is saved in a JSON file For Easier access instead of Database queries saves and deletes. Currently Delete sets the report inactive in the JSON file which will prevent it from being in the menu but will need to be removed manually until I sort that out better!



## Config

```lua
Config = {}

Config.wasabi_ambulance = true -- if false put your event below. uses Player.source for WHO to revive

Config.ReviveEvent = 'esx_ambulancejob:revive' -- only if not using wasabi_ambulance!

Config.Notifications = {
    client = 'ox',
    server = 'ox'
}

Config.CommandInfo = {

    ['open'] = {

        command = 'openReport',

    },

    ['adminOpen'] = {

        command = 'adminReports'

    }
    
}

Config.AllowedGroups = {

    ["admin"] = true,
    -- add more if you wish to add other groups
    -- ["mod"] = true
}
```

{% hint style="info" %}
Dependencies:

\~ Ox\_libs\
\~ ESX For Admin Groups
{% endhint %}

