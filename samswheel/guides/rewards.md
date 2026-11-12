---
description: Everything a wheel can hand out, and how the odds works!
icon: trophy
---

# Rewards

## How Rewards Work

Each wheel has a list of rewards under `rewards:` in its `wheels/<id>.yml`. When a player spins, the server picks a reward first (by **weight**), then animates the wheel to land on it, so the visible result always matches the real outcome.

A wheel renders one segment per **active** reward (2–12). A reward is active when `enabled: true`.

***

## Weights & Chance

`chance` is a **weight**, not a fixed percentage. A reward's real win chance is its weight divided by the total weight of all active rewards.

{% hint style="info" %}
#### Good to know!

Example: weights of `25`, `30`, `30`, `15` total `100`, so they win `25%`, `30%`, `30%`, `15%`. If you disable one, the others' real chances rise automatically.
{% endhint %}

***

## Reward Fields

```json
rewards:
  diamonds:
    display-name: "<#55FFFF>5 Diamonds <#555555>(<chance>)"
    chance: 25.0
    enabled: true
    segment-color: "24b6c4"          # wheel wedge colour (BLOCKS style)
    permission: ""                    # optional; blank = anyone can win it
    message: "<green>You won 5 Diamonds!" # optional per-win message
    sound: "minecraft:entity.player.levelup 1 1" # optional per-win sound
    commands:
      - "give %player% diamond 5"
    lore:
      - "<gray>A handful of the good stuff."
    icon:
      material: DIAMOND
      amount: 5
      glow: false
```

| Field           | Meaning                                                              |
| --------------- | -------------------------------------------------------------------- |
| `display-name`  | The reward's name label. Supports colours and `<chance>` / `<name>`. |
| `chance`        | Weight used for the draw (see above).                                |
| `enabled`       | Whether the reward is active (gets a segment).                       |
| `segment-color` | Wedge colour in `BLOCKS` appearance style.                           |
| `permission`    | If set, only players with it can win this reward.                    |
| `message`       | Message sent to the winner (blank = default).                        |
| `sound`         | Sound played on this specific win.                                   |
| `commands`      | Console commands run on win.                                         |
| `lore`          | Lines shown under the reward name in the world.                      |
| `icon`          | The item shown on the segment (see below).                           |

***

## Reward Commands

Commands in the `commands:` list run from **console** when the reward is won. Placeholders:

* `%player%` -> the winner's name
* `%reward%` -> the reward's display name
* `%wheel%` -> the wheel's display name

```json
commands:
  - "eco give %player% 10000"
  - "give %player% diamond_block 1"
```

***

## Items Save (Exact vs Simple)

When you **add a reward** or press **Pick from inventory**, a popup asks **how the item should be saved** before the inventory picker opens:

| Mode                         | What is stored                                                                                                                                                    |
| ---------------------------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **Exact copy** (recommended) | A byte-for-byte copy everything the item carried is kept: enchantments, custom name, lore, potion effects, custom model data and any other NBT / data components. |
| **Simple**                   | Only the plain `material` / `amount` (and model data), so you can freely edit the fields by hand.                                                                 |
