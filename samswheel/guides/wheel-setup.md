---
description: Design a whole wheel without touching a config file!
icon: poker-chip
---

# Wheel Setup

## Opening the Editor

Run `/samswheel editor` (permission `samswheel.editor`). Look around to **move** the cursor, left-click to **select**, scroll/drag on sliders, and press F to **close**.

{% hint style="info" %}
#### Wheel Editor

Pick a wheel from the list to open its editor. On the right you'll always see a **Live Preview** that updates as you edit.
{% endhint %}

***

## Editor Sections

The sidebar splits a wheel into focused sections:

<details>

<summary><strong>General</strong></summary>

Display name, permission, enable/disable, and the optional server-wide win broadcast.

</details>

<details>

<summary><strong>Location</strong></summary>

Move the primary wheel here, face it toward you, and add or remove extra copies, one wheel definition can render in several places, all spinning in sync.

</details>

<details>

<summary><strong>Rewards</strong></summary>

Open the reward list to add, edit and remove prizes. See [Rewards](rewards.md).

</details>

<details>

<summary><strong>Animation</strong></summary>

Spin duration, revolutions and the easing/motion style. See [Animations & Win Effects](animations-and-win-effects.md).

</details>

<details>

<summary><strong>Cost &#x26; Ticket</strong></summary>

Choose how players pay, the fields shown adapt to the cost type. See [Cost & Tickets.](cost-and-tickets.md)

</details>

<details>

<summary><strong>Cooldown</strong></summary>

Wait time between spins and the concurrency mode (one at a time vs. everyone at once).

</details>

<details>

<summary><strong>Appearance</strong></summary>

Wheel design (theme), size, and rim/hub/arrow colours. See [Appearance & Designs](appearance-and-designs.md).

</details>

<details>

<summary><strong>Reward Items</strong></summary>

Show/hide reward items and names, item size, spin-with-wheel vs. stay-upright alignment, name visibility mode, and 2D/3D block display.

</details>

<details>

<summary><strong>Holograms</strong></summary>

The floating title above the wheel. See [Holograms & Labels](holograms-and-labels.md).

</details>

<details>

<summary><strong>Sounds</strong></summary>

Sounds for spin start, ticking, landing and winning.

</details>

<details>

<summary><strong>Particles / Effects</strong></summary>

The ambient particles and the win-effect celebration.

</details>

***

## Saving

Changes apply live to the preview. Press **Save & apply** to write the wheel's `wheels/<id>.yml` and respawn the physical wheel with your changes.

{% hint style="success" %}
#### Saves

Everything you set in the editor is stored in plain YAML, so you can also edit `wheels/<id>.yml` by hand and `/samswheel reload`.
{% endhint %}
