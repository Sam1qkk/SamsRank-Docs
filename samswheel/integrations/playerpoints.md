---
description: Here you can learn how PlayerPoints support works!
icon: tickets-perforated
---

# PlayerPoints

## PlayerPoints

Use [PlayerPoints](https://www.spigotmc.org/resources/playerpoints.80745/) points as the price of a spin.

***

## Setting It Up

{% stepper %}
{% step %}
#### Open the wheel's Cost & Ticket section

Run `/samswheel editor`, pick your wheel and open **Cost & Ticket**.
{% endstep %}

{% step %}
#### Choose PlayerPoints

Click **Cost type** and pick **PlayerPoints**. If it's shown in red as **NOT INSTALLED**, PlayerPoints isn't on the server (or didn't load).
{% endstep %}

{% step %}
#### Set the price

Enter how many points one spin costs in the amount field.
{% endstep %}
{% endstepper %}

***

## In the wheel file

```yaml
cost:
  type: POINTS
  amount: 50      # 50 points per spin
```

`PLAYERPOINTS` and `PLAYER_POINTS` work as type names too.
