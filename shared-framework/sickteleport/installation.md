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

# Installation

### Usable Items

```lua
Config.UsableItems = {
    'location_setter'
}
```

In the Config.lua you can change the items used to teleport to anything you wish. If you are creating a new item I have provided a small template to help you get going. Any item in here will be able to access the menu including `water` if you set that.&#x20;

{% hint style="info" %}
Example item:

```lua
--[[ ( ( -EXAMPLE ITEM FOR OX- ) )

	['location_setter'] = {
		label = 'Teleporter',
		weight = 115,
		description = 'Go Somewhere'
	},

]]
```
{% endhint %}



### SQL

To use and create home locations you need to create the database table. Here will store WHO the home location is for the Set Home Location and the Set Home Name. These variables are all changed by using the script. The Default one needs to be there as SQL is funny but its a small hiccup.&#x20;



{% hint style="danger" %}
ALWAYS keep one home location in the databases. If not the script will error.
{% endhint %}

{% code title="sql.sql" %}
```sql
CREATE TABLE IF NOT EXISTS `sickteleports` (
  `citizenid` varchar(60) NOT NULL,
  `hashome` varchar(5) DEFAULT '0',
  `homelocations` varchar(250) DEFAULT NULL,
  `homeName` tinytext DEFAULT 'Home',
  PRIMARY KEY (`citizenid`) USING BTREE
) ENGINE=InnoDB DEFAULT CHARSET=latin1 COLLATE=latin1_swedish_ci ROW_FORMAT=DYNAMIC;
```
{% endcode %}

In case you ever need a back up one I will leave one here:

```sql
INSERT INTO `sickteleports` (`citizenid`, `hashome`, `homelocations`, `homeName`) VALUES
	('WKI50V48', '1', '{"x":-1063.014404296875,"y":-861.290771484375,"z":4.86802625656127}', 'SickScripts');
```
