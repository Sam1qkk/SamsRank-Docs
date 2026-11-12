---
description: Every player feels the season. Settings live in gameplay/temperature.yml.
icon: temperature-high
---

# Temperature

## How It Works?

Every `update-seconds` (2 s), SamsSeasons works out each player's temperature in °C by adding up everything around them (below). The shown temperature doesn't jump: it drifts towards the new value by at most `smoothing` degrees per update, so stepping into a house warms you up over a few seconds.

The result falls into a **band** (freezing, cold, cool, comfortable, warm, hot, scorching), and the band decides what the player feels. `/seasons temperature` lists every part of the sum, so players can see _why_ they're cold.

***

### What Affects It

All of these are under `climate:`:

* **`biome`**: the biome's own climate, from its vanilla temperature: plains about 12 °C, taiga 4, desert 30, snowy plains 0, frozen peaks -7.
* **`seasons`**: added per season and phase (spring -2 to 4, summer 6 to 9, autumn 2 to -5, winter -8 to -11).
* **`dimensions`**: the Nether is hot, the End is cold.
* **`day-night`**: nights are colder than noon.
* **`altitude`**: high up is colder (per 10 blocks).
* **`rain`, `thunder`**: bad weather under the open sky cools you.
* **`water`, `wet`**: swimming cools you a lot, and you stay wet for a while after leaving the water.
* **`activity`**: sprinting warms you up.
* **`block-light`, `heat-sources`**: campfires, fire, lava, furnaces, magma and other warm blocks nearby.
* **`shelter`**: a roof and walls soften the weather and the night.
* **`clothing`**: leather keeps you warm in the cold; heavy armour makes heat worse.
* **Warm food**: stews, soups and honey warm you for a while (`extras.food`); several stack.
* **Admin and region changes**: `/seasons temperature modify <player> <degrees> <seconds>`, the API, and the WorldGuard offset flag.

***

### What Players Feel

Each band starts `below` a temperature and can have its own consequences:

| Band        | Below | Default effect                                                                                                  |
| ----------- | ----- | --------------------------------------------------------------------------------------------------------------- |
| Freezing    | -1 °C | Vanilla freezing (frost overlay, then freeze damage; leather protects). Frost sound and snowflakes now and then |
| Cold        | 6 °C  | Shivers now and then; breath clouds below 0 °C                                                                  |
| Cool        | 12 °C | Nothing                                                                                                         |
| Comfortable | 26 °C | Nothing                                                                                                         |
| Warm        | 32 °C | Cosy: slowly heals (when not hungry)                                                                            |
| Hot         | 40 °C | Faster hunger, sweat drops                                                                                      |
| Scorching   | above | Much faster hunger, Weakness, small flames and fire sounds                                                      |

What a band can do:

| Key          | What it does                                                                     |
| ------------ | -------------------------------------------------------------------------------- |
| `freeze`     | Vanilla freezing: frost creeps over the screen, then it hurts like powder snow   |
| `exhaustion` | Extra hunger per update                                                          |
| `effects`    | Potion effects while in the band, e.g. `["SLOWNESS:0", "WEAKNESS:0"]`            |
| `heal`       | Health given back per update (only when not hungry)                              |
| `sound`      | A sound now and then: `"entity.player.hurt_freeze 0.4 1.0"` (key, volume, pitch) |
| `particle`   | Particles at the player now and then: `"SNOWFLAKE 4"` (name, count)              |
| `chance`     | Chance (0-1) per update for the sound and particle                               |

```yaml
bands:
  freezing:
    below: -1
    freeze: true
    sound: "entity.player.hurt_freeze 0.35 1.0"
    particle: "SNOWFLAKE 4"
    chance: 0.35
  warm:
    below: 32
    heal: 0.2
```

`extras:` adds the little touches: breath clouds in the cold, sweat drops in the heat, and warm food.

***

### The Action Bar

```yaml
actionbar: uncomfortable      # always | uncomfortable | never
actionbar-format: ""          # empty = the language file's temperature.actionbar
```

* **`actionbar`**: `always` keeps it on screen, `uncomfortable` shows it only when cold or hot, `never` turns it off for everyone.
* **`actionbar-format`**: your own text. Placeholders: `%icon%`, `%temperature%`, `%feeling%`, `%season%`, `%phase%`, `%date%`, and any PlaceholderAPI placeholder. Colour codes and `&#RRGGBB` work.
* Players can hide it for themselves with `/seasons actionbar off` (and bring it back with `on`).

```yaml
actionbar: always
actionbar-format: "%icon% &f%temperature% &8| %season% &8| &7%date%"
```

***

### More..

* `unit: celsius | fahrenheit` changes what players see.
* Creative and spectator players, and anyone with `samsseasons.bypass.temperature`, are never affected.
* Switch temperature off in a region with the WorldGuard flag, or inside claimed land with claims.

{% hint style="info" %}
Placeholders: `%samsseasons_temperature%`, `%samsseasons_temperature_raw%`, `%samsseasons_temperature_feeling%`, `%samsseasons_temperature_icon%`.
{% endhint %}
