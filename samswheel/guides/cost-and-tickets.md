---
description: Choose how players pay to spin!
icon: sack-dollar
---

# Cost & Tickets

## Cost Types

Set the cost type in the editor's **Cost & Ticket** section (or `cost.type` in YAML). The editor only shows the fields relevant to the type you pick.

{% tabs %}
{% tab title="Type: FREE" %}
Anyone who may use the wheel can spin it at no cost.
{% endtab %}

{% tab title="Type: TICKET/ITEM" %}
The player must have the wheel's **ticket item**; it is **consumed** on spin.
{% endtab %}

{% tab title="Type: VAULT" %}
Costs money via **Vault** and an economy plugin.
{% endtab %}

{% tab title="Type: FREE_SPIN" %}
Lets a player always spend a free spin regardless of the cost type, handy for vote/reward spins on a paid wheel.&#x20;
{% endtab %}
{% endtabs %}

***

## The Ticket Item

For `TICKET` and `ITEM` cost types, the required item is fully customisable in the editor's ticket screen (with a live preview) or under `ticket:` in YAML:

```json
ticket:
  material: PAPER
  amount: 1
  name: "<#FFAA00><bold>Daily Wheel Ticket</bold>"
  lore:
    - "<gray>Right-click the Daily Wheel to spin."
  glow: true
  customModelData: 0
  itemModel: ""
```

You can add up to five lore lines at a glance in the editor, with a scrollbar for longer lists.

***

## Cooldown & Concurrency

In the **Cooldown** section:

* **Cooldown** -> the wait before a player can spin again (e.g. `24h`, `90m`, `0` for none). Reset a player with `/samswheel resetcooldown <player> <wheel>`.
* **Spin mode**
  * **One at a time** -> only one player may spin this wheel at once.
  * **Everyone at once** -> concurrent spinners are resolved independently, with rewards delivered safely even if a player logs off mid-spin.

{% hint style="warning" %}
#### Prizes Store

Undelivered prizes are stored and handed out when the player next joins, so nobody loses a win to a disconnect.
{% endhint %}
