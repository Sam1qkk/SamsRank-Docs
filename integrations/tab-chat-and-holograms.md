---
description: Here you can learn how TAB, Chat and Holograms support works!
icon: rocketchat
---

# TAB, Chat & Holograms

## TAB, Chat & Holograms

Tips for showing rank tags in the most common plugins.

***

### TAB

Use the placeholder in the tablist or nametag prefix, for example in TAB's `groups.yml`:

```yaml
owner:
  tabprefix: "%samsrank_aurora_owner% "
  tagprefix: "%samsrank_aurora_owner% "
```

{% hint style="info" %}
TAB reads PlaceholderAPI directly, so SamsRank always gives it the real tag character, never an ItemsAdder `:rank:` tag that TAB would show literally (except for a brand-new ItemsAdder rank until `/iazip` has finished).
{% endhint %}

If TAB warns about **legacy formatting codes**, set `placeholders.output-format: minimessage`

***

### LuckPerms Prefixes & Chat

Set the placeholder as a group prefix:

```
/lp group owner meta setprefix 100 "%samsrank_owner% "
```

Your chat plugin (and TAB) must parse PlaceholderAPI inside prefixes. MiniMessage-based chat plugins work best with `output-format: minimessage`.

***

### Holograms

* **FancyHolograms** -> detected automatically; SamsRank outputs MiniMessage-safe text.
* **DecentHolograms** -> detected automatically; SamsRank uses DecentHolograms' own RGB format so effects keep their exact colour.

Just use the normal placeholder, e.g. `%samsrank_starlight_owner%`, in a hologram line.
