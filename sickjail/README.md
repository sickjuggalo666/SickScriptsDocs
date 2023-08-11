# 🔒 SickJail

{% embed url="https://www.youtube.com/embed/razYYRyOq1s" %}
(Video is VERY outdated and from the start of this project. Just an EXAMPLE of whats to come!)
{% endembed %}

**Welcome to SickJail. SickJail is a VERY interactive jail system for your Cities!**

**There are lots of different things you are able to do with it.**

**Ranging from Gang system to legal jobs.**

**There is a ton of options built in to the jail to give your players more to do while they do hefty sentences!**



## SQL:

There are a few things you will need to do before using the script!

{% hint style="info" %}
Make sure you do this before starting the script! This stores the info you will need while Jail is running
{% endhint %}

```sql
CREATE TABLE IF NOT EXISTS `sickPrisonGangs` (
    `id` int(11) NOT NULL AUTO_INCREMENT,
    `identifier` varchar(60) DEFAULT NULL,
    `gang` varchar(250) DEFAULT NULL,
    `reputation` smallint(6) NOT NULL DEFAULT 0,
    PRIMARY KEY (`id`) USING BTREE
) ENGINE=InnoDB AUTO_INCREMENT=304 DEFAULT CHARSET=latin1 ROW_FORMAT=DYNAMIC;

ALTER TABLE users ADD COLUMN 'jail' int(15) NOT NULL DEFAULT 0;
```



## Items:

Add all items to Ox\_Inventory/data/items.lua

{% code lineNumbers="true" %}
```lua
Items = {
    
	['prison_meal'] = {
		label = 'Prison Meal',
		weight = 150,
		stack = true,
		close = true,
		description = 'Yummm prison food'
	},

    ['ingredients'] = {
		label = 'Ingredients',
		weight = 150,
		stack = true,
		close = true,
		description = 'Idk you figure it out'
	},

    ['marlborocig'] = {
		label = 'Marlboro Cig',
		weight = 150,
		stack = true,
		close = true,
		description = 'Mmmm the burn in your lungs!'
	},

    ['mud'] = {
		label = 'Mud',
		weight = 150,
		stack = true,
		close = true,
		description = 'A NASTY susbstance'
	},

    ['hooch'] = {
		label = 'Hooch',
		weight = 150,
		stack = true,
		close = true,
		description = 'Still Nasty but better'
	},

    ['rotten_oranges'] = {
		label = 'Rotten Oranges',
		weight = 150,
		stack = true,
		close = true,
		description = 'These were left out a little long'
	},

    ['drugbag'] = {
		label = 'Drug Bag',
		weight = 150,
		stack = true,
		close = true,
		description = 'The Ole Prison Wallet'
	},

	['plastic'] = {
		label = 'Plastic Pieces',
		weight = 150,
		stack = true,
		close = true,
		description = 'I\'m sure you can find a use'
	},

	['wood'] = {
		label = 'Drug Bag',
		weight = 150,
		stack = true,
		close = true,
		description = 'Setting fires, making shanks'
	},
	
	['shovel'] = {
		label = 'Shovel',
		weight = 150,
		stack = true,
		close = true,
		description = 'Digging you know'
	},

	['cup_of_noodles'] = {
		label = 'Cup Of Noodles',
		weight = 150,
		stack = true,
		close = true,
		description = 'Yummmm the Best Ever'
	},
}
```
{% endcode %}





{% tabs %}
{% tab title="Legal Jobs" %}
There is a range of legal jobs you are able to do for money or items that can be used to obtain items not so easily gotten in prison! Adds more to the feel of being in prison but actually being a model inmate!



1. Cook (Kitchen Position where you cook meals and turn them in for Money or Items)&#x20;
2. Electrician (Fix the boxes around the yard to earn Money)&#x20;
3. Infirmary (Some Crazy inmate made a mess, it sucks but clean it up for a Reward!)&#x20;
4. Trash (Check Barrels and run trash bags and get money and maybe a random item hidden!)&#x20;
5. Toilets (Clean the toilets in the unit these people are messy!
{% endtab %}

{% tab title="Gang Jobs" %}
Gang jobs will be choosen randomly. Some are easy some are more difficult! Do more work for the Gangs and find your self rewarded with more options and better items!



1. Hooch (Grab the stuff needed to mix and head to the cell and whip up a batch, the Gangs will love this!)&#x20;
2. Shiv (Someone hid a Shiv on the yard, find it and there is a nice reward!)&#x20;
3. Snitches (We all know what snitches get, so go handle it!)
4. Bunks (Everyone out a yard so search the bunks there was talk of a shipment coming in)
{% endtab %}
{% endtabs %}



## Other Info:



{% hint style="danger" %}
Inventory: \
\
Inventory is automatically taken when entering Prison and returned to player upon release! This makes entering and exiting prison that much smoother for server owners and players!
{% endhint %}

{% hint style="danger" %}
Target:&#x20;

\
Every thing is ran off Ox\_Target. All Jobs, tasks, peds and even Jail Menu! Global Player option for police to open the menu from the closest player! All Targets have an InJail Check that will not let you interact unlesss you are in jail!
{% endhint %}
