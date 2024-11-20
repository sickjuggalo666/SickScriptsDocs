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

# Default Locations

In the Config there is a table containing the Default Locations that you can set. These are the locations available when ever the menu is opened by both Donators and Citizens. These can be changed/deleted to fit your server needs.

```lua
Config.DefaultLocations = {
    [1] = {
        label = 'Los Santos',
        coords = {x=64.6316,y=-1336.1709,z=29.3015},
        heading = 266.1323,
    },
    [2] = {
        label = 'Los Santos 2',
        coords = {x=77.5215,y=-1353.1078,z=29.4189},
        heading = 222.8532,
    }
}
```
