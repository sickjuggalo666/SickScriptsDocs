# Boss Menu

One of the most important steps is the boss men. In order for this to work I made an edit to esx\_society! Super easy to do and a small walk through will be provided!



## ESX\_SOCIETY

Here I will show the small edits to esx\_society that will make you able to use this portion. This also makes it easier for you to use in other scripts instead of base events!

In esx\_society client.lua Search for:

```lua
AddEventHandler('esx_society:openBossMenu', function(society, close, options)
	OpenBossMenu(society, close, options)
end)
```

Above or Below this handler add this snippet of code:

```lua
exports('openBossMenu',function(society, close, options)
	OpenBossMenu(society, close, options)
end)
```

From here you can now use this export in any script Example usage:

```lua
exports.esx_society:openBossMenu(JOB, BOOLEAN, options)
```

```lua
exports.esx_society:openBossMenu(job, true, {
    withdraw = true, 
    deposit = true, 
    wash = false, 
    employees = true, 
    grades = true
})
```
