# 🎯 Newest ESX

When Updating to newer ESX versions they removed the CB for getSharedObject. This was to utilize the much faster export, but with that many people have scripts that are locked and impossible for you to update to the export! Below will be a few Steps to follow to help you get updated to newest ESX while still using your older scripts!      &#x20;

There will be two files that we will need to edit!\
&#x20; 1\. client/common.lua

2. server/common.lua                                                                                                                                                  &#x20;

![](<../.gitbook/assets/image (3).png>)![](<../.gitbook/assets/image (3) (1).png>)

In both of these files you will find this snippet of code:

{% code title="client/common.lua 9-12" lineNumbers="true" %}
```lua
AddEventHandler("esx:getSharedObject", function()
	local Invoke = GetInvokingResource()
	print(("[^1ERROR^7] Resource ^5%s^7 Used the ^5getSharedObject^7 Event, this event ^1no longer exists!^7 Visit https://documentation.esx-framework.org/tutorials/tutorials-esx/sharedevent for how to fix!"):format(Invoke))
end)
```
{% endcode %}

{% code title="server/common.lua 16-19" lineNumbers="true" %}
```lua
AddEventHandler("esx:getSharedObject", function()
	local Invoke = GetInvokingResource()
	print(("[^1ERROR^7] Resource ^5%s^7 Used the ^5getSharedObject^7 Event, this event ^1no longer exists!^7 Visit https://documentation.esx-framework.org/tutorials/tutorials-esx/sharedevent for how to fix!"):format(Invoke))
end)
```
{% endcode %}

As is these will just print that the getSharedObject event has been depricated and to use the new export! These two snippets we will change by pasting the bellow snippet inside both events! Examples below:

{% code title="CallBack The Object" %}
```lua
cb(ESX)
```
{% endcode %}

Final product for both Events should look like:

{% code title="client/common.lua 9-12" lineNumbers="true" %}
```lua
AddEventHandler("esx:getSharedObject", function(cb) --make sure the cb is there!
    cb(ESX)
end)
```
{% endcode %}

{% code title="server/common.lua 16-19" lineNumbers="true" %}
```lua
AddEventHandler("esx:getSharedObject", function(cb) --make sure the cb is there!
    cb(ESX)
end)
```
{% endcode %}

![](<../.gitbook/assets/image (4).png>)

Little Video to help SEE what you need to do better!!

{% embed url="https://streamable.com/raig4l" %}
