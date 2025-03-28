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

# Config

There are a couple new options to use for Particles. This should make it easier for you to add many weapons quicker! You can still of course use the default way of per weapon if you choose to have it on say 1 of 1 weapons!

<figure><img src="../../.gitbook/assets/image (1).png" alt=""><figcaption></figcaption></figure>

{% hint style="danger" %}
Beware you can only use ONE option below.&#x20;

If both are false you will use default WeaponsTable
{% endhint %}

## <mark style="color:red;">Weapon Groups</mark>

With the weapon groups you can group all weapons that have the same class. Meaning all weapons classed as pistol will be able to use the particles. This makes it easier to add many weapons while still limiting some like Rocket Launchers.&#x20;

```lua
Config.WeaponGroups = {
    ['GROUP_RIFLE'] = {
        asset = 'scr_fbi3',
        Particle = "scr_indep_fireworks",
    },
    ['GROUP_PISTOL'] = {
        asset = 'scr_fbi3',
        Particle = "scr_indep_fireworks",
    }
}
```

## <mark style="color:red;">Ammo Types</mark>

With ammo types you can limit this to just certain ammos. These are default GTA Ammos and are mainly based on the weapon group. You can use WeaponGroups to accomplish the same thing basically but is an option if you prefer.&#x20;

```lua
Config.AmmoTypes = {
    ['AMMO_RIFLE'] = {
        asset = 'scr_fbi3',
        Particle = "scr_fbi3_elec_sparks",
    },
}
```



## <mark style="color:red;">Weapon Table</mark>

The Weapons table is where you can set the different weapons you want and the particles you want associated with that weapon. This is the default way the script is used!

```lua
Config.Weapons = { -- only used if config.UseGroupTypes and Config.UseAmmoType is false
    ["WEAPON_PISTOL"] = {
        WeaponItem = "WEAPON_PISTOL",
        asset = 'scr_fbi3',
        Particle = "scr_indep_fireworks",
    },
    ["WEAPON_GLOCK"] = {
        WeaponItem = "WEAPON_GLOCK",
        asset = 'scr_fbi3',
        Particle = "scr_indep_fireworks",
    },
    ["WEAPON_ASSAULTRIFLE"] = {
        WeaponItem = "WEAPON_ASSAULTRIFLE",
        asset = 'scr_indep_fireworks',
        isColored = true,
        Particle = "scr_indep_firework_burst_spawn",
        color = {6, 241, 53} -- color only works on certain particles finding new system for color
    },
}
```
