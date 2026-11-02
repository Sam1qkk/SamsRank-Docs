---
description: Here you can learn how ItemsAdder and Nexo support works!
icon: paintbrush
---

# ItemsAdder & Nexo

## ItemsAdder & Nexo

If you run [ItemsAdder](https://itemsadder.devs.beer) or [Nexo](https://nexomc.com), SamsRank puts its ranks straight into their resource pack, nothing to merge by hand.

***

## What SamsRank Does

On `/samsrank convert` (and whenever the editor saves a rank), SamsRank:

* writes the rank textures and configs into the platform's folders,
* installs the effect shaders into the pack,
* and on `/samsrank reload` asks the platform to rebuild and re-send its pack (`iareload` + `iazip` on ItemsAdder, `nexo reload` on Nexo).

| Platform   | SamsRank installs into                                                                                                        |
| ---------- | ----------------------------------------------------------------------------------------------------------------------------- |
| ItemsAdder | `plugins/ItemsAdder/contents/sams_creations/` (configs in `configs/sams_rank/`, textures in `resourcepack/assets/sams_rank/`) |
| Nexo       | `plugins/Nexo/pack/external_packs/sams_creations/` (textures) and `plugins/Nexo/glyphs/sams_creations/sams_rank/` (glyphs)    |

If **both** are installed, `platform.preferred` in `config.yml` chooses `itemsadder`, `nexo` or `both`.
