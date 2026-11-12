---
description: The floating title above the wheel, and the reward name labels!
icon: image
---

# Holograms & Labels

## Floating Title

Each wheel can show a floating title hologram above it, configured in the editor's **Holograms** section (`appearance.hologram` in YAML).

```json
hologram:
  enabled: true
  background: default       # "default", "none", or ARGB hex like "aa000000"
  scale: 1.1
  billboard: FIXED
  lines:
    - "<#FFAA00><bold><name></bold>"
    - "<gray>Right-click to spin"
```

* **Lines** support MiniMessage colours and the `<name>` placeholder (the wheel's display name).
* **Background** -> the vanilla text box, transparent, or a custom ARGB colour.
* **Scale** -> overall size of the title.

***

## Title Facing (billboard)

| Mode         | Behaviour                                             |
| ------------ | ----------------------------------------------------- |
| `FIXED`      | Faces the front of the wheel and never turns.         |
| `CENTER`     | Always turns to face whoever is looking.              |
| `VERTICAL`   | Turns left/right toward the player but stays upright. |
| `HORIZONTAL` | Lies flat and turns on the horizontal plane.          |

***

## Reward Name Labels

Reward names sit just below each item on the wheel. Configure them in **Reward Items**:

* **Show reward items / names** -> toggle the icons and their name labels.
* **Item alignment** -> _Spin with wheel_ (rotate with the segment) or _Stay upright_ (stay level as they travel).
* **Item size** -> a size multiplier for the reward icons.
* **Name gap** -> the distance a name sits below its item (`reward-name-distance`).
* **Name background** -> how the name label's backing looks (`reward-name-background`): `default` (vanilla text box), `none` (transparent/invisible), or an ARGB hex like `a0080808`

***

## Name Visibility (`reward-name-mode`)

| Mode     | When names show                                  |
| -------- | ------------------------------------------------ |
| `ALWAYS` | Names are always visible.                        |
| `LOOK`   | Only while a player is looking at the wheel.     |
| `ITEM`   | Only the specific item the player is looking at. |

{% hint style="info" %}
#### &#x20;Big Wheels

`LOOK` and `ITEM` keep busy wheels clean, names appear on demand instead of crowding the face.
{% endhint %}
