---
description: Here you can learn how WorldGuard support works!
icon: shield-quartered
---

# WorldGuard

## WorldGuard

With [WorldGuard](https://enginehub.org/worldguard) installed, SamsSeasons registers its own region flags. Everything is allowed by default, so you only set the flags where you want a feature off.

| Flag                             | Type         | What it controls                                                        |
| -------------------------------- | ------------ | ----------------------------------------------------------------------- |
| `samsseasons-temperature`        | allow / deny | Players feel the temperature here                                       |
| `samsseasons-temperature-offset` | number       | Degrees added here (e.g. `10` for a warm tavern, `-15` for an ice cave) |
| `samsseasons-particles`          | allow / deny | Seasonal particles appear here                                          |
| `samsseasons-snow`               | allow / deny | Seasonal snow and ice settle here                                       |
| `samsseasons-crops`              | allow / deny | Seasonal crop growth applies here (deny = vanilla growth)               |
| `samsseasons-mobs`               | allow / deny | Seasonal mob spawning and variants apply here                           |

***

## Examples

```
/rg flag spawn samsseasons-snow deny
/rg flag spawn samsseasons-temperature deny
/rg flag tavern samsseasons-temperature-offset 8
```

{% hint style="info" %}
Keeping snow out of spawn is a common one: your spawn build stays clean all winter while the rest of the world turns white.
{% endhint %}
