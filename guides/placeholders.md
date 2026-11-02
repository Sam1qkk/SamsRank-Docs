---
description: Every SamsRank tag is a PlaceholderAPI placeholder!
icon: percent
---

# Placeholders

## Placeholders

| Placeholder                  | Shows                                 |
| ---------------------------- | ------------------------------------- |
| `%samsrank_<rank>%`          | The rank tag.                         |
| `%samsrank_<effect>_<rank>%` | The rank tag with an animated effect. |

```
%samsrank_owner%
%samsrank_aurora_owner%
%samsrank_blaze_vip%
```

{% hint style="success" %}
`/samsrank list` shows every rank, click one to copy its placeholder. `/samsrank effects` lists every effect name.
{% endhint %}

***

## Using Them

Put the placeholder wherever your server shows a rank:

* **LuckPerms prefix** -> e.g. `/lp group owner meta setprefix 100 "%samsrank_aurora_owner% "`&#x20;
* **TAB** -> in the tablist or nametag prefix.
* **Chat formats**, **scoreboards** and **holograms**.

***

## Output Format

By default SamsRank outputs legacy colour codes and switches to the right format for FancyHolograms and DecentHolograms on its own. If your chat or TAB plugin reads placeholders as **MiniMessage** and complains about legacy codes, switch the format:

```yaml
placeholders:
  output-format: minimessage   # auto | minimessage | legacy
```

| Value         | Output                                                                                   |
| ------------- | ---------------------------------------------------------------------------------------- |
| `auto`        | Legacy colour codes, with automatic MiniMessage / DecentHolograms handling. (default)    |
| `minimessage` | Always `<color:#rrggbb>` - for TAB, MiniMessage chat and LuckPerms MiniMessage prefixes. |
| `legacy`      | Always legacy colour codes, no auto-detection.                                           |
