# 🏨 SickApartmentSelect

SickApartmentSelect is a super simple script that works with PS-Housing and Multichar scripts that bypass PS-Housing starter apartment section. This will allow your players to still claim ONE free apartment in the city!

{% hint style="danger" %}
{% code title="Run The Following SQL:" %}
```sql
ALTER TABLE `players` ADD COLUMN IF NOT EXISTS pickedApart smallint(5) NOT NULL DEFAULT 0;
```
{% endcode %}
{% endhint %}

After creating your character you are granted ONE free apartment in the city! These Apartments need to be picked by you from the guy at the job center! There are a few to pick from so find one you like!

<figure><img src="../.gitbook/assets/image (1) (1).png" alt=""><figcaption></figcaption></figure>

After selecting the one you would like a window will open to ask you to verify you actually want this one.&#x20;

<figure><img src="../.gitbook/assets/image (2) (1).png" alt=""><figcaption></figcaption></figure>

After confirming you want the Apartment it will fly you straight to it! You will get your first look at your new place!&#x20;
