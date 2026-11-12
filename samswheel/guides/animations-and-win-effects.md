---
description: Make the spin feel great and the win feel special!
icon: sparkle
---

# Animations & Win Effects

## The Spin

In the editor's **Animation** section (`animation:` in YAML):

* **Duration** -> how long the spin lasts, in ticks (`duration-ticks`).
* **Revolutions** -> how many full turns before it lands (`revolutions`).
* **Easing** -> the motion curve.

| Easing     | Feel                                    |
| ---------- | --------------------------------------- |
| `OUT`      | Smooth decelerate to a stop (classic).  |
| `INOUT`    | Ease in, then ease out.                 |
| `LINEAR`   | Constant speed, hard stop.              |
| `MOMENTUM` | Overshoots the slot, then springs back. |
| `PULSE`    | Rhythmic surges with a final impact.    |

{% hint style="success" %}
#### In-Game Showcase

Use the **Play spin in preview** button in the editor to watch the motion **without** leaving the menu.&#x20;
{% endhint %}

***

## Win Effects

When a reward is won, SamsWheel plays a celebration on the physical wheel. Set the type in the **Effects** section (`win-effect.type`):

| Type        | What happens                                    |
| ----------- | ----------------------------------------------- |
| `NONE`      | No effect.                                      |
| `PARTICLES` | A particle celebration (choose a style below).  |
| `FIREWORK`  | Coloured firework rockets.                      |
| `ROCKET`    | The reward launches upward, then bursts.        |
| `BURST`     | Copies of the reward burst outward.             |
| `DROP`      | The reward drops into the centre with a bounce. |
| `SHOWCASE`  | The reward is presented, slowly rotating.       |
| `SPIRAL`    | Particles spiral in and converge on the reward. |

For the `PARTICLES` type, pick a **particle style** (`win-effect.particle-style`): `BURST`, `RING`, `SPIRAL`, `FOUNTAIN`, `EXPLOSION`, `FALLING`, `RADIAL` or `REWARD`.

```json
win-effect:
  type: ROCKET
  particle-style: BURST
```

{% hint style="success" %}
#### In-Game Showcase

The editor has a **Test** button that plays the selected win effect on the real wheel so you can dial it in.
{% endhint %}

***

## Sounds & Ambient Particles

* **Sounds** -> set the spin start, ticking, slowdown, landing and win sounds in the **Sounds** section (`sounds:`).
* **Ambient particles** -> a subtle particle effect around an idle wheel (`particles:`).
