---
description: Here you can learn how ExcellentEconomy support works!
icon: coin-blank
---

# ExcellentEconomy

## ExcellentEconomy

Use any [ExcellentEconomy](https://modrinth.com/plugin/excellenteconomy) currency coins, gems, tokens, shards.. as the price of a spin. Different wheels can use different currencies.

***

## Setting It Up

{% stepper %}
{% step %}
#### Open the wheel's Cost & Ticket section

Run `/samswheel editor`, pick your wheel and open **Cost & Ticket**.
{% endstep %}

{% step %}
#### Choose ExcellentEconomy

Click **Cost type** and pick **ExcellentEconomy**. If it's shown in red as **NOT INSTALLED**, ExcellentEconomy isn't on the server (or didn't load).
{% endstep %}

{% step %}
#### Pick the currency

Enter the **currency id** in the currency field for example `coins` or `gems`. The editor warns you if ExcellentEconomy has no currency with that id.
{% endstep %}

{% step %}
#### Set the price

Enter how much of that currency one spin costs in the amount field.
{% endstep %}
{% endstepper %}

***

## In the wheel file

```yaml
cost:
  type: CURRENCY
  currency: gems  # the ExcellentEconomy currency id
  amount: 100     # 100 gems per spin
```

`EXCELLENTECONOMY`, `EXCELLENT_ECONOMY` and `COINSENGINE` work as type names too.

{% hint style="warning" %}
`currency` is the currency's **id** (its file name / ID in ExcellentEconomy), not its display name. If you leave it out it defaults to `coins`.
{% endhint %}
