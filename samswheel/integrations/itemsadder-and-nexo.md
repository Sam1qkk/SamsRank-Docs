---
description: Here you can learn how ItemsAdder and Nexo support works!
icon: pencil
---

# ItemsAdder & Nexo

## ItemsAdder & Nexo

SamsWheel needs a resource pack for its wheel textures and the in-game editor. If you run [ItemsAdder](https://itemsadder.devs.beer) or [Nexo](https://nexomc.com), SamsWheel puts its assets straight into their pack, nothing to merge by hand.

***

## Automatic pack merging

| Platform   | SamsWheel installs into                                |
| ---------- | ------------------------------------------------------ |
| ItemsAdder | `plugins/ItemsAdder/contents/sams_wheel/resourcepack/` |
| Nexo       | `plugins/Nexo/pack/external_packs/sams_wheel/`         |

If **both** are installed, `platform.preferred` in `config.yml` chooses `itemsadder`, `nexo` or `both`.

{% hint style="info" %}
No ItemsAdder or Nexo? SamsWheel can host its own pack see Resource Pack Provider.
{% endhint %}

***

## Custom items as reward icons

Reward icons can be ItemsAdder or Nexo items. Use a prefix instead of a vanilla material:

```yaml
icon:
  material: "itemsadder:my_namespace:ruby"   # or "ia:..."
```

```yaml
icon:
  material: "nexo:ruby_sword"
```
