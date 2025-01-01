# QBCore Users

If you are using QBCore we need to handle the zones/peds a bit differently as qb-target isn't the best at handling the zones outside of their script. With that we need to make edits to our qb-target to make this work



By Setting `Config.Target`  to `qb-target`  it will inform the script that we are using that target system and make it skip parts like creating peds at certain locations. This is handled now IN `qb-target`  itself.&#x20;



Head to `qb-target/init.lua` and scroll down until you find `Config.Peds` this is where we will now place our peds and edit the target to your liking.&#x20;

{% code lineNumbers="true" %}
```lua
Config.Peds = {
	[1] = { -- This MUST be a number (UNIQUE), if you make it a string it won't be able to delete peds spawned with the export
		model = 's_m_m_armoured_01', -- This is the ped model that is going to be spawning at the given coords
		coords = vector4(445.4416, -996.6559, 30.6896, 0.0636), -- This is the coords that the ped is going to spawn at, always has to be a vector4 and the w value is the heading
		minusOne = true, -- Set this to true if your ped is hovering above the ground but you want it on the ground (OPTIONAL)
		freeze = true, -- Set this to true if you want the ped to be frozen at the given coords (OPTIONAL)
		invincible = true, -- Set this to true if you want the ped to not take any damage from any source (OPTIONAL)
		blockevents = true, -- Set this to true if you don't want the ped to react the to the environment (OPTIONAL)
		animDict = 'abigail_mcs_1_concat-0', -- This is the animation dictionairy to load the animation to play from (OPTIONAL)
		anim = 'csb_abigail_dual-0', -- This is the animation that will play chosen from the animDict, this will loop the whole time the ped is spawned (OPTIONAL)
		flag = 1, -- This is the flag of the animation to play, for all the flags, check the TaskPlayAnim native here https://docs.fivem.net/natives/?_0x5AB552C6 (OPTIONAL)
		scenario = 'WORLD_HUMAN_AA_COFFEE', -- This is the scenario that will play the whole time the ped is spawned, this cannot pair with anim and animDict (OPTIONAL)
		target = { -- This is the target options table, here you can specify all the options to display when targeting the ped (OPTIONAL)
			useModel = false, -- This is the option for which target function to use, when this is set to true it'll use AddTargetModel and add these to al models of the given ped model, if it is false it will only add the options to this specific ped
			options = { -- This is your options table, in this table all the options will be specified for the target to accept
				{ -- This is the first table with options, you can make as many options inside the options table as you want
				num = 1, -- This is the position number of your option in the list of options in the qb-target context menu (OPTIONAL)
				type = "client", -- This specifies the type of event the target has to trigger on click, this can be "client", "server", "command" or "qbcommand", this is OPTIONAL and will only work if the event is also specified
				event = "SickEvidence:openInventory", -- This is the event it will trigger on click, this can be a client event, server event, command or qbcore registered command, NOTICE: Normal command can't have arguments passed through, QBCore registered ones can have arguments passed through
				icon = 'fas fa-door-open', -- This is the icon that will display next to this trigger option
				label = 'Open Locker', -- This is the label of this option which you would be able to click on to trigger everything, this has to be a string
				targeticon = 'fas fa-door-open', -- This is the icon of the target itself, the icon changes to this when it turns blue on this specific option, this is OPTIONAL
				canInteract = function(entity, distance, data) -- This will check if you can interact with it, this won't show up if it returns false, this is OPTIONAL
					return true
				end,
				job = 'police', -- This is the job, this option won't show up if the player doesn't have this job, this can also be done with multiple jobs and grades, if you want multiple jobs you always need a grade with it: job = {["police"] = 0, ["ambulance"] = 2},
				}
			},
			distance = 2.5, -- This is the distance for you to be at for the target to turn blue, this is in GTA units and has to be a float value
		},
	},
	[2] = { -- This MUST be a number (UNIQUE), if you make it a string it won't be able to delete peds spawned with the export
		model = 'IG_BallasOG', -- This is the ped model that is going to be spawning at the given coords
		coords = vector4(425.7189, -985.5151, 30.7109, 1.2687), -- This is the coords that the ped is going to spawn at, always has to be a vector4 and the w value is the heading
		minusOne = true, -- Set this to true if your ped is hovering above the ground but you want it on the ground (OPTIONAL)
		freeze = true, -- Set this to true if you want the ped to be frozen at the given coords (OPTIONAL)
		invincible = true, -- Set this to true if you want the ped to not take any damage from any source (OPTIONAL)
		blockevents = true, -- Set this to true if you don't want the ped to react the to the environment (OPTIONAL)
		animDict = 'abigail_mcs_1_concat-0', -- This is the animation dictionairy to load the animation to play from (OPTIONAL)
		anim = 'csb_abigail_dual-0', -- This is the animation that will play chosen from the animDict, this will loop the whole time the ped is spawned (OPTIONAL)
		flag = 1, -- This is the flag of the animation to play, for all the flags, check the TaskPlayAnim native here https://docs.fivem.net/natives/?_0x5AB552C6 (OPTIONAL)
		scenario = 'WORLD_HUMAN_AA_COFFEE', -- This is the scenario that will play the whole time the ped is spawned, this cannot pair with anim and animDict (OPTIONAL)
		target = { -- This is the target options table, here you can specify all the options to display when targeting the ped (OPTIONAL)
			useModel = false, -- This is the option for which target function to use, when this is set to true it'll use AddTargetModel and add these to al models of the given ped model, if it is false it will only add the options to this specific ped
			options = { -- This is your options table, in this table all the options will be specified for the target to accept
				{ -- This is the first table with options, you can make as many options inside the options table as you want
					num = 1, -- This is the position number of your option in the list of options in the qb-target context menu (OPTIONAL)
					type = "client", -- This specifies the type of event the target has to trigger on click, this can be "client", "server", "command" or "qbcommand", this is OPTIONAL and will only work if the event is also specified
					event = "SickEvidence:openInventory", -- This is the event it will trigger on click, this can be a client event, server event, command or qbcore registered command, NOTICE: Normal command can't have arguments passed through, QBCore registered ones can have arguments passed through
					icon = 'fas fa-door-open', -- This is the icon that will display next to this trigger option
					label = 'Open Locker', -- This is the label of this option which you would be able to click on to trigger everything, this has to be a string
					targeticon = 'fas fa-door-open', -- This is the icon of the target itself, the icon changes to this when it turns blue on this specific option, this is OPTIONAL
					canInteract = function(entity, distance, data) -- This will check if you can interact with it, this won't show up if it returns false, this is OPTIONAL
						return true
					end,
					gang  = 'ballas', -- This is the job, this option won't show up if the player doesn't have this job, this can also be done with multiple jobs and grades, if you want multiple jobs you always need a grade with it: job = {["police"] = 0, ["ambulance"] = 2},
				}
			},
			distance = 2.5, -- This is the distance for you to be at for the target to turn blue, this is in GTA units and has to be a float value
		},
	},
}
```
{% endcode %}

Copy this into your table.. if its an empty table you can use the whole table I provided above.

{% hint style="danger" %}
If you already have peds on the `Config.Peds` then make sure to change the index number to match what you have already!\
\
Also make sure `Config.Target = 'qb-target'` in SickLockers otherwise you will have duplication issues and errors from other systems.&#x20;
{% endhint %}

{% hint style="info" %}
Adding new peds for lockers is SUPER easy. Simply copy a job table and change the variables to match the new job you have set.&#x20;
{% endhint %}
