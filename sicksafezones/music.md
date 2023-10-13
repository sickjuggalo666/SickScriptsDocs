# Music

Setting up music for your zones is as easy as setting the Config option to `true`

```lua
Config.UseZoneMusic = true
```

Next Find a dope link from YouTube that you would like playing while in the Zones

{% code lineNumbers="true" %}
```lua
Config.MusicInfo = {
    [1] ={
        name = 'safezone1',
        link = 'https://www.youtube.com/watch?v=YUoHI2gDf7k',
        volume = 0.4,
        coords = vector3(696.2985, 130.9088, 83.8779),
        distance = 75
    },
    --[[[2] ={
        name = 'safezone2',
        link = 'https://www.youtube.com/watch?v=d_uqlELD4qw',
        volume = 0.3,
        coords = vector3(1699.2564, 3771.0712, 34.524211),
        distance = 37
    },]]
}
```
{% endcode %}

Add more zones by just copying the table and changing variables.&#x20;
