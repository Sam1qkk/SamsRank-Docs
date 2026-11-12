---
description: How does it all works?
icon: gamepad-modern
---

# Gameplay

## Gameplay

How the seasons change survival. These files live in `plugins/SamsSeasons/gameplay/`. Each has an `enabled` switch at the top, and almost every value can be set per season (`winter: 0`) or per phase (`autumn: { early: 1.0, mid: 0.8, late: 0.5 }`). For the default values of each season, see The Four Seasons.

{% hint style="info" %}
**Reading the numbers:** `1.0` = vanilla, `1.4` = 40% faster or more, `0.5` = half, `0` = not at all.
{% endhint %}

***

### Crops (`crops.yml`)

**How it works:** Minecraft grows plants in random "growth ticks". Each time a crop is about to grow, SamsSeasons looks at its group's `growth` for the current phase. Above `1.0` the crop sometimes gets an extra growth step, below `1.0` some growth steps are cancelled, and at `0` it doesn't grow at all.

* **Groups**: field crops, gourds (pumpkins, melons), berries, sugar cane / cactus / bamboo, cocoa... each with its own blocks and speeds.
* **Greenhouses**: a crop with any glass block or pane straight above it (within `max-height` blocks) grows at least at the greenhouse `growth`, whatever the season. This is how players farm through winter.
* **Harvest bonus**: breaking a fully grown plant has a chance (`harvest-bonus`) of extra drops, mostly in autumn.

***

### Animals (`animals.yml`)

**How it works:** when two animals are fed to breed, `breeding-chance` decides whether a baby actually comes. The food is used either way, the way real seasons work. With `twin-chance` a second baby appears, and `cooldown` stretches or shortens the time until the parents can breed again (× the vanilla 5 minutes).

Each animal type can have its own values: bees and frogs don't breed in winter, wolves don't care about the season.

### Mobs (`mobs.yml`)

**How it works:** only **natural** spawns are touched (`reasons: [NATURAL]`). Spawners, spawn eggs, breeding and other plugins' mobs are left alone.

* **Spawn rates**: below `1.0`, some natural spawns of that mob are cancelled; above `1.0`, extra ones appear next to natural ones.
* **Variants**: a natural mob is sometimes replaced, e.g. skeletons under the open sky become **strays** in winter, zombies in hot biomes become **husks** in summer. Options: `chance`, `outdoors-only`, `min-biome-temperature`.

### Wildlife (`wildlife.yml`)

**How it works:** every `interval` (30 s) SamsSeasons tries to spawn seasonal animals a little away from each player (`radius` 24-48 blocks), in suitable biomes, but never more than `max-nearby` of one kind. Out of the box: wolves, foxes and polar bears in winter, bees, rabbits and frogs in spring, foxes in autumn.

Seasonal animals wander off again (they despawn when nobody is near) unless a player tames, names or leashes them. In spring, animals near players also have babies; in late autumn, some monsters wear a pumpkin on their head.

***

### Fishing (`fishing.yml`)

**How it works:** `bite-speed` changes how long a player waits for a bite (`1.25` = bites 25% sooner). When a fish is caught, `bonus-chance` decides whether it's replaced by one of the season's **special catches**, picked by `weight`.

* Each catch has a name, lore, weight, XP and an optional `item-model` / `custom-model-data`. With the resource pack, every catch has its own icon.
* Give a catch with `/seasons give <player> <season> <catch> [amount]`. The editor addon shows them all as items.

```yaml
catches:
  spring:
    blossom-salmon:
      material: SALMON
      name: "&#F2B5D4Blossom Salmon"
      lore: ["&7Caught among drifting petals."]
      weight: 10
      xp: 6
```

***

## Also..

* Temperature: how players feel the cold and heat.
* Festivals: special days with perks and rewards.
* Switch crops, mobs or temperature off per area with WorldGuard or inside claims.
