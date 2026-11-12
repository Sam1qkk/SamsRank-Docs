---
description: >-
  Everything that makes the world look like the season. These files live in
  plugins/SamsSeasons/atmosphere/.
icon: stars
---

# Seasonal Visuals

## Seasonal Visuals

Everything that makes the world _look_ like the season. These files live in `plugins/SamsSeasons/atmosphere/`. For what each season looks like out of the box, see The Four Seasons.

***

## Grass, Leaves, Water & Sky (`biomes.yml`)

Each biome gets seasonal grass, foliage, water, sky and fog colours, plus snowfall instead of rain in winter and optional ambient particles.

#### How It Works

{% stepper %}
{% step %}
#### A seasonal copy of every biome

When the server starts, before the worlds load, SamsSeasons writes a small datapack with a copy of each biome for every season phase (spring early, spring mid... winter late), with only the colours and weather changed. It registers the pack by itself: there's nothing to install, and it works on the very first start.
{% endstep %}

{% step %}
#### Players are shown the copy

The real world never changes. When a chunk is sent to a player, PacketEvents lets SamsSeasons swap each biome in that packet for its copy of the current phase. The client then draws the grass, leaves and water in the seasonal colours.
{% endstep %}

{% step %}
#### The land turns slowly

When the phase changes, the new look spreads patch by patch: `transition.seconds` (15 s) in `transition.steps` (5) steps, re-sending the chunks around each player a few at a time (`refresh.chunks-per-tick`).
{% endstep %}
{% endstepper %}

Because only packets change, removing SamsSeasons leaves your world exactly as it was: same biomes, same terrain, same mob spawning.

{% hint style="warning" %}
Without PacketEvents the seasons still run, but the land keeps its vanilla colours. Changes to the groups in `biomes.yml` need a **server restart**, because biomes are registered before the worlds load.
{% endhint %}

***

### Groups, Shades and Defaults

* **Groups** are biomes that change together: temperate, taiga, swamp, jungle, savanna, snowy, coast and dry. Each group sets its colours per season and, where needed, per phase.
* **Colours** are either exact (`"#D9702B"`) or blended into the biome's own colour (`"#D9702B 60%"`), which keeps forests and plains looking different from each other.
* **Shades**: give a list of colours and they are mixed across the land in patches (`variation.patch-size`), so a winter forest has pure white, icy blue, silver and frosty mint instead of one flat white.
* **Defaults** apply to every group underneath its own values. Out of the box this gives all water a seasonal look: bright in spring, turquoise in summer, murky in autumn, dark and icy in winter.

***

### Datapack Biomes (Terralith, Arboria...)

Biomes added by datapacks get seasonal colours too. On startup SamsSeasons reads the datapacks in your main world's `datapacks` folder (folders and zip files) and gives each new biome the seasons of the group whose climate it matches:

| A datapack biome that is...                          | follows the group |
| ---------------------------------------------------- | ----------------- |
| an ocean, beach or coast                             | `coast`           |
| a swamp, marsh, bog or mangrove                      | `swamp`           |
| a desert, dune, badlands or canyon                   | `dry`             |
| frozen or very cold (snowy, glacier, tundra, alpine) | `snowy`           |
| hot and without rain                                 | `savanna`         |
| hot and very wet (jungle, rainforest)                | `jungle`          |
| cool (taiga, pine, boreal)                           | `taiga`           |
| anything else                                        | `temperate`       |

It judges by the biome's name and its temperature, downfall and rain settings. The startup log says how many datapack biomes got seasons.

To pick a look yourself, add the biome with its namespace to a group:

```yaml
groups:
  taiga:
    biomes: [taiga, old_growth_pine_taiga, "terralith:alpine_grove"]
```

Turn the automatic part off with `datapack-biomes.enabled: false`. Restart the server after adding or removing a datapack.

***

### Block Swaps

Spruce, birch, cherry and pale oak leaves keep a fixed colour in vanilla; the client ignores biome colours for them. `block-swaps` shows players one leaf block as another, again purely visually:

```yaml
block-swaps:
  cherry-blossom:
    from: oak_leaves
    to: cherry_leaves
    when: [spring_early, spring_mid]
    share: 0.45          # part of the trees that blossom
  birch-autumn:
    from: birch_leaves
    to: oak_leaves       # so birches take the seasonal golds and whites
    when: [autumn, winter]
    share: 1.0
```

Blossoming trees come in natural, rounded groups. At the edge of a group, pink and green leaves mix leaf by leaf, so no tree is cut in half. Breaking a "cherry" oak leaf still drops oak leaves, because the block really is oak.

***

## Particles (`particles.yml`)

Falling leaves in the season's colours, cherry petals from pink trees, snow drifting from branches, snowfall, pollen and fireflies.

**How it works:** every `interval-ticks` (4 ticks), SamsSeasons checks a few random spots within `radius` (14 blocks) of each player, the effect's `samples` times its current strength. A spot only counts if it fits the effect:

* **`leaf-drop`** (leaves, petals, snow from branches): the spot must be under a tree canopy that hangs over air. The particle starts just under the lowest leaf. Petals only fall from leaves that _look_ pink (cherry trees and blossoming oaks).
* **`sky`** (snowfall, pollen): open sky above the player.
* **`ground`** (fireflies): just above grass or flowers.

So the amount follows the landscape: under a dense forest you see many leaves, next to one tree only a few. Particles are sent only to that player, and never more than `max-per-player` per run, so a full server costs about the same as a handful of players.

* Strength per season or phase: `autumn: { early: 0.5, mid: 1.0, late: 1.3 }`.
* Filters: `time` (day/night), `weather` (clear/storm), `biomes`, `exclude-biomes`.
* `colors` per season for tinted particles; with the resource pack, nicer leaf and snowflake sprites.
* Players can turn particles off for themselves with `/seasons particles off`.

***

### Snow & Ice (`snow.yml`)

Real snow layers settle on the ground and water freezes, in a `radius` (48 blocks) around players, a few blocks at a time. How fast it settles is set per phase. When it's `0` (in spring, by default), the snow starts to melt.

**Nothing is ever lost:** every snow layer and ice block SamsSeasons places is written down in its chunk. When it melts, only those blocks are removed, and only if they are still snow or ice. Natural snow, ice and anything players built are never touched. The thaw happens by chance, one layer at a time, so snow fades away in patches. Chunks nobody visits during the thaw melt the moment they're loaded again.

Keep snow off spawn or players' bases with WorldGuard or claims.

### Weather (`weather.yml`)

Every Minecraft day gets its own weather, drawn from the season's `rain-chance` and `storm-chance`: dry, or rain (snow in cold places) for part of the day, sometimes a thunderstorm. Days are planned ahead, so `/seasons forecast` shows what will really happen. `/weather` still works and wins until the next day. Worlds with the `doWeatherCycle` game rule off are left alone.

### Day Length (`daylight.yml`)

Long winter nights and short summer nights. Time never runs backwards: SamsSeasons only speeds up one part of the day (`day-speed`, `night-speed`), so the other part lasts relatively longer. Sleeping, `/time` and other plugins keep working. Worlds with `doDaylightCycle` off are left alone.

### Night Sky (`sky.yml`)

On clear nights, players under the open sky now and then see a shooting star streak by (mostly in summer) or an aurora shimmer over the horizon (in winter). Only the player who looks up sees it, so it costs almost nothing.

### Blooms (`blooms.yml`)

Wild flowers pop up on the grass in spring, and mushrooms in autumn forests. Every couple of seconds SamsSeasons tries a few spots around each player. When the season ends they wither away again, but only the ones SamsSeasons planted, and only if they're still there. Picking them is fine.

### Ambience (`ambience.yml`)

Birdsong on spring mornings, crickets on summer nights, rustling autumn leaves and the winter wind. A sound plays for each player every 10-25 seconds, a few blocks away. Players hear it on the _Ambient/Environment_ volume slider. Without the resource pack a vanilla sound plays; with it you can replace the sounds with your own recordings (see `internal/resourcepack/overrides/README.txt`).
