---
description: Design rank tags online at ranktags.samscreations.eu!
icon: weebly
---

# Web Generator

## The Web Editor

[ranktags.samscreations.eu](https://ranktags.samscreations.eu) is SamsRank's online rank designer. Run `/samsrank generator` in-game for a clickable link.

* **Templates** - 10+ professionally designed tag styles.
* **Icons** - 25+ icons with their own colours and backgrounds.
* **Colours** - solid colours, gradients with any angle, and hex colours, for the tag and the icon.
* **Live preview** - see every change instantly.
* **Community gallery** - browse, use and save ranks other players made, or share your own.
* **Design history** - look at your previous tags and track changes.

Download the finished PNG, drop it into `plugins/SamsRank/ranks/` and run `/samsrank convert` - see the Conversion Tutorial.

***

## Generate from a Command

```
/samsrank generate <name> [key:value ...]
```

The rank name may only use lowercase letters, numbers, `-` and `_`. The PNG is saved into `ranks/` and converted automatically.

| Key                  | Values                                                                                                                                                                                                                                                                                       |
| -------------------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| `style`              | `rounded`, `squared`, `extra-rounded`, `medieval`, `cartoon`, `classic`, `hourglass`, `legacy`, `modern`, `tapered`                                                                                                                                                                          |
| `color`              | Tag colour (hex)                                                                                                                                                                                                                                                                             |
| `colorMode`          | `solid` or `gradient`                                                                                                                                                                                                                                                                        |
| `gradientColors`     | Gradient colours for the tag                                                                                                                                                                                                                                                                 |
| `gradientAngle`      | Gradient angle for the tag                                                                                                                                                                                                                                                                   |
| `icon`               | `squires`, `crown`, `crown2`, `information_mark`, `computer`, `hammer`, `crystal`, `bubble`, `star`, `play_button`, `shield`, `shield2`, `shield3`, `user`, `cup`, `chestplate`, `chestplate2`, `crate`, `crate2`, `crate3`, `circle`, `house`, `heart`, `question_mark`, `skull`, `compass` |
| `iconStyle`          | Icon background style (same values as `style`)                                                                                                                                                                                                                                               |
| `iconColorMode`      | `solid` or `gradient`                                                                                                                                                                                                                                                                        |
| `iconColor`          | Icon colour (hex)                                                                                                                                                                                                                                                                            |
| `iconGradientColors` | Gradient colours for the icon                                                                                                                                                                                                                                                                |
| `iconGradientAngle`  | Gradient angle for the icon                                                                                                                                                                                                                                                                  |
| `iconColorSync`      | `true` / `false` - icon uses the tag's colours                                                                                                                                                                                                                                               |
| `iconBgSync`         | `true` / `false` - icon background follows the tag                                                                                                                                                                                                                                           |
