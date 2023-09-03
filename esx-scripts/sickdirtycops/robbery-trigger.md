# Robbery Trigger

Here I will show some examples of ways to use the event to let the menu know that they Robbery is open or if it has recently been robbed!





{% tabs %}
{% tab title="Server Trigger" %}
```
TriggerClientEvent('SickDirtyCops:UpdateRobberyChecks', source, BOOLEN)
```
{% endtab %}

{% tab title="Client Trigger" %}
```
TriggerEvent('SickDirtyCops:UpdateRobberyChecks', BOOLEN)
```
{% endtab %}
{% endtabs %}
