---
description: Here you can learn how claims support works!
icon: location-arrow
---

# Claims

## Lands, Factions & GriefPrevention

Players often don't want seasonal snow on their bases, or seasonal mob changes inside their town. With a land-claim plugin installed, you can switch chosen features off inside **claimed land**, while the wild world keeps all of them.

Supported, detected automatically:

* **Lands**
* **Factions**: FactionsUUID, SaberFactions and other forks that keep the classic Factions API
* **GriefPrevention**

***

### Setup

In `config.yml`:

```yaml
integrations:
  claims:
    enabled: true
    disable-inside: [snow]
```

`disable-inside` lists what is switched off inside any claim:

| Value         | Inside claims                              |
| ------------- | ------------------------------------------ |
| `snow`        | No seasonal snow and ice is placed         |
| `temperature` | Players don't feel the temperature         |
| `particles`   | No seasonal particles                      |
| `crops`       | Crops grow at vanilla speed                |
| `mobs`        | Vanilla mob spawning, no seasonal variants |

Leave the list empty (the default) and claims change nothing. Run `/seasons reload` after changing it.

{% hint style="info" %}
Snow that already lies in a claim isn't removed when you add `snow` here; it melts normally in spring. Claimed land just stops getting new snow.
{% endhint %}

***

### How It Works

Whenever SamsSeasons is about to do one of these things at a spot (place snow, show a particle, apply a temperature, grow a crop, change a spawning mob), it asks the installed claim plugins whether that spot is claimed. Faction land counts as claimed; Wilderness doesn't. The check works with the claim plugins' own data, so new claims count immediately.

For finer control per area, use WorldGuard flags; both work together.
