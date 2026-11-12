---
description: Here you can learn how WorldGuard support works!
icon: shield-quartered
---

# WorldGuard

## WorldGuard

With [WorldGuard](https://enginehub.org/worldguard) installed, SamsWheel adds a region flag so you decide where wheels can be spun.



|               |                                                               |
| ------------- | ------------------------------------------------------------- |
| **Flag name** | `samswheel-use`                                               |
| **Type**      | State flag (`allow` / `deny`)                                 |
| **Default**   | `allow` -> wheels work everywhere until you deny it somewhere |

When the flag is denied, the spin is refused before anything is paid and the player gets the `spin.region-denied` message.

***

## Some Examples

Block spinning in a region:

```
/rg flag spawn samswheel-use deny
```

Only let region members spin there:

```
/rg flag shop -g nonmembers samswheel-use deny
```

Go back to the default:

```
/rg flag spawn samswheel-use
```
