---
description: Animated shader effects for your rank tags!
icon: sparkle
---

# Rank Effects

## How It Works

SamsRank installs a custom text shader into your resource pack. Each effect has its own (almost white) trigger colour; when a tag is drawn in that colour, the shader animates it. You never deal with colours yourself.. just put the effect name in the placeholder:

```
%samsrank_<effect>_<rank>%
```

For example `%samsrank_starlight_admin%` shows the `admin` tag with a diagonal shimmer.

{% hint style="success" %}
Run `/samsrank effects` to preview every effect on the example rank, or use the effect preview in the in-game editor.
{% endhint %}

***

## All Effects

| Effect      | What it does                                        |
| ----------- | --------------------------------------------------- |
| `starlight` | Classic diagonal shimmer, top-left to bottom-right. |
| `moonbeam`  | Reverse diagonal shimmer, bottom-right to top-left. |
| `rainfall`  | Vertical shimmer, top to bottom.                    |
| `whisper`   | Slow, smooth shimmer with a gentle wave.            |
| `blaze`     | Fast glitch with crack distortion.                  |
| `aurora`    | Colour-cycling diagonal shimmer.                    |
| `gilded`    | Warm gold shimmer with an edge rim and wave.        |
| `breathe`   | Subtle rhythmic fade pulse.                         |
| `tide`      | Slow horizontal shimmer with a wave.                |
| `neon`      | Edge shimmer with a glow outline.                   |
| `ripple`    | Waving motion with a vertical shimmer.              |
| `drift`     | Slow sliding with a diagonal shimmer.               |
| `ember`     | Micro-glitch with a reversed shimmer.               |
| `pendulum`  | Slow swaying, like a hanging sign.                  |
| `pulse`     | Slow expand and contract.                           |
| `wander`    | Characters rise one by one in a slow wave.          |
| `phantom`   | Slow fade with a whisper of edge glow.              |

***

## Turning Effects Off

Prefer static tags, or want to save client GPU? One switch turns every effect off:

```yaml
effects:
  enabled: false
```

Effect placeholders then show the plain tag (`%samsrank_aurora_owner%` looks like `%samsrank_owner%`), **and** the effect shaders are left out of the generated pack entirely. Run `/samsrank reload` and regenerate your platform pack after changing it.

***

## Where Effects Show

Effects render wherever Minecraft draws text with the pack's font: chat, TAB, scoreboards, nametags, holograms and BetterHud elements (see BetterHud).

{% hint style="info" %}
Bedrock players see the static tag - effects are a Java shader feature. See Bedrock (Geyser).
{% endhint %}
