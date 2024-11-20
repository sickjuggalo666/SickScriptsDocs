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

# Weapons

The Weapons table is where you can set the different weapons you want and the particles you want associated with that weapon

```lua
Config.Weapons = {
    [1] = {
        WeaponItem = "WEAPON_PISTOL",
        asset = 'scr_fbi3',
        Particle = "scr_fbi3_elec_sparks",
    },
    [2] = {
        WeaponItem = "WEAPON_ASSAULTRIFLE",
        asset = 'scr_indep_fireworks',
        isColored = true,
        Particle = "scr_indep_firework_burst_spawn",
        color = {6, 241, 53} -- color only works on certain particles finding new system for color
    },
}
```

```lua
    [1] = {
        WeaponItem = "WEAPON_PISTOL", -- the weapon item
        asset = 'scr_fbi3', -- the particle asset
        Particle = "scr_fbi3_elec_sparks", -- and the particle to use
        color = {6, 241, 53} -- color only works on certain particles finding new system for color
    }
```
