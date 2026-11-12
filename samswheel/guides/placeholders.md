---
description: List of all placeholders!
icon: percent
---

# Placeholders

## Available Placeholders

| Placeholder                           | Returns                                        |
| ------------------------------------- | ---------------------------------------------- |
| `%samswheel_total_spins%`             | Server-wide total spins.                       |
| `%samswheel_total_rewards%`           | Server-wide total rewards handed out.          |
| `%samswheel_spins_<wheel>%`           | Total spins on a specific wheel.               |
| `%samswheel_cooldown_<wheel>%`        | The player's remaining cooldown on a wheel.    |
| `%samswheel_last_reward_<wheel>%`     | The player's last reward on a wheel.           |
| `%samswheel_ticket_<wheel>%`          | How many tickets the player holds for a wheel. |
| `%samswheel_freespins_<wheel>%`       | The player's stored free spins for a wheel.    |
| `%samswheel_chance_<wheel>_<reward>%` | A reward's live win chance, e.g. `12.50%`.     |

Replace `<wheel>` with a wheel id (e.g. `daily`) and `<reward>` with a reward id from that wheel's `rewards:` map.

***

## In-Wheel Text

Inside reward names and hologram lines you can also use SamsWheel's own inline placeholders (no PAPI needed):

* `<name>` -> the wheel's display name.
* `<chance>` -> the reward's live win % (reward text only).

```json
display-name: "<#55FFFF>5 Diamonds <#AAAAAA>(<chance>)"
```
