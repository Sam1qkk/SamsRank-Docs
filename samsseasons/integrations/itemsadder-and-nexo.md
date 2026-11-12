---
description: Here you can learn how ItemsAdder and Nexo support works!
icon: pen
---

# ItemsAdder & Nexo

## How It Works

With `resource-pack.provider: auto` (the default):

* **Nexo installed**: the pack is copied into Nexo's external packs and `nexo pack` runs to rebuild it.
* **ItemsAdder installed**: the pack is copied into ItemsAdder's contents and `iazip` runs.
* **Neither**: SamsSeasons hosts the pack itself.

The rebuild only runs when SamsSeasons' files actually changed, once, a few seconds after startup, so it doesn't fight with other plugins' reloads.

You can also force one with `provider: nexo` or `provider: itemsadder`, or use `manual` to only generate the folder and serve it yourself.

***

## Custom Models in Menus and Catches

The season menu, the calendar and the fishing catches accept `item-model` and `custom-model-data`, so you can use models from your ItemsAdder or Nexo pack directly:

```yaml
item-model: "myserver:frost_cod"
```
