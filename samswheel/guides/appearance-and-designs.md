---
description: Style the wheel face, and add your own designs!
icon: palette
---

# Appearance & Designs

## Bundled Designs

TEXTURE style ships with six themes (`appearance.variant`):

| Variant   | Look                                                      |
| --------- | --------------------------------------------------------- |
| `default` | Rainbow segments with white dividers, brown rim, gold hub |
| `ornate`  | Gold-rimmed                                               |
| `casino`  | Red/black roulette                                        |
| `neon`    | Glowing                                                   |
| `royale`  | Red & cream spokes, ornate gold rim                       |
| `rainbow` | Wooden rim with gold studs, rainbow segments              |

***

## Size & Colours

* **Wheel size** -> resize the whole wheel in the editor's Appearance section (1-5 block radius). It's stored as `appearance.radius`.
* **Rim / Centre / Arrow colours** -> hex colours for the frame, hub and pointer (`frame-color`, `hub-color`, `pointer-color`).

***

## Different Back

By default the wheel shows a **texture** on its reverse side. Toggle it with **Different back** in the editor's Appearance section, or `appearance.show-back` in YAML.

```yaml
appearance:
  show-back: true      # false = the reverse mirrors the front, as before
  back-offset: 0.09    # how far the back sits behind the front, in blocks (config-only)
```

* **`back-offset`** controls the space between the two sides.

Custom designs can ship a back by adding a `back.png` (64×64) to their folder; without one, that design simply has no distinct back.

***

## Adding Your Own Designs

You don't need to edit code or wait for an update to add a design.

{% stepper %}
{% step %}
### Create a Folder

Under `plugins/SamsWheel/wheel-designs/`, make a folder named after your design (lowercase, no spaces), e.g. `wheel-designs/mydesign/`.&#x20;
{% endstep %}

{% step %}
### Add the Texture

Put 64×64 PNGs inside named `wheel_2.png` through `wheel_12.png` one per segment count. `wheel_N.png` is used when a wheel has N rewards.&#x20;
{% endstep %}

{% step %}
### Reload & Apply

Run `/samswheel reload`, then regenerate/re-apply your resource pack.
{% endstep %}
{% endstepper %}

{% hint style="warning" %}
#### Same Names

Names that match a built-in design (`default`, `ornate`, `dark`, `casino`, `neon`, `rustic`, `prize`) are ignored, pick a unique name. A `README.txt` in the folder repeats these steps.
{% endhint %}
