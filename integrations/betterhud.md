---
description: Here you can learn how BetterHud support works!
icon: image
---

# BetterHud

## BetterHud

Use SamsRank's animated tags together with [BetterHud](https://github.com/toxicity188/BetterHud).

***

### Why It Needs an Integration?

BetterHud draws its HUD with its own copy of Minecraft's text shader, the same shader SamsRank uses for rank effects. Two resource packs can't both replace one shader.

***

### How It Works

When BetterHud is installed, SamsRank **doesn't ship its own text shader**. It plugs its effect code into BetterHud's shader through BetterHud's API instead, and BetterHud does the final drawing. One shader, and both the HUD and the animated tags work, on every version BetterHud supports (1.21.4 up to 26.3).

* Automatic - nothing to configure.
* BetterHud's shader is rebuilt for you on startup and on `/samsrank reload`.
* `/samsrank report` shows `betterhud-shader-hook` and `betterhud-owns-text-shader`.

***

### Setup

{% stepper %}
{% step %}
#### Install both plugins

Install BetterHud and SamsRank, then restart.
{% endstep %}

{% step %}
#### Make sure both packs reach players

BetterHud's resource pack must reach players **together with** SamsRank's for example both merged through ItemsAdder or Nexo.
{% endstep %}

{% step %}
#### Reload

Run `/samsrank reload`. If BetterHud's HUD still looks off, run `/hud reload` too, then regenerate your pack and rejoin.
{% endstep %}
{% endstepper %}

***

### Turning It Off

Installed BetterHud but don't use its resource pack? Set:

```yaml
integrations:
  betterhud: false
```

SamsRank then ships its own text shader again. Run `/samsrank reload` after changing it.
