# SetUp

{% hint style="success" %}
SQL:&#x20;

`ALTER TABLE` owned\_vehicles`ADD COLUMN`twostep `INT(11) NOT NULL DEFAULT '0';`
{% endhint %}

## Items:

If you are using Ox\_inventory I have provided the needed code to add to items.lua. If you are not using Ox\_inventory then use the provided sql to add the item to your DataBase!

{% tabs %}
{% tab title="Not Using Ox_Inventory" %}
```sql
INSERT INTO `items` VALUES (`name`,`label`,`weight`)
('2step', '2Step Module', 10),
('2step_checker', '2Step Module Checker', 10);
```
{% endtab %}

{% tab title="Using Ox_Inventory" %}
<pre class="language-lua"><code class="lang-lua"><strong>['2step'] = {
</strong>	label = '2Step Module',
	weight = 1,
	stack = true,
	close = true,
	description = 'Bang Bang'
},
['2step_Checker'] = {
	label = '2Step Module Checker',
	weight = 1,
	stack = true,
	close = true,
	description = 'For Checking 2Step Modules'
},
</code></pre>
{% endtab %}
{% endtabs %}
