---
description: How to use the built-in rank manager and pixel editor
icon: computer-speaker
---

# In-Game Editor

## In-Game Interface

Manage, design and edit rank tags without leaving the game or touching a config file.

{% hint style="info" %}
#### **How to open it**

Run `/samsrank` (or `/samsrank menu`) to open the manager. To jump straight into a rank, use `/samsrank edit <rank>`.
{% endhint %}

***

## Controls

* **Cursor**: look around with your mouse to move the cursor. Sensitivity is in `config.yml` (`ui.cursor.sensitivity`).
* **Left Click**: select tools, press buttons, paint pixels.
* **Right Click**: secondary tool actions (like painting with the secondary colour).
* **Scroll Wheel**: zoom, or cycle through effect presets.
* **Sneak (Shift) + Scroll**: change the brush size.
* **F (Swap Hands)**: close the interface. **Q (Drop)**: go back.

{% hint style="info" %}
F, Q and Shift can be rebound in `config.yml` under `ui.keybinds` (actions: `close`, `back`, `home`, `none`).
{% endhint %}

***

## What You Can Do

* **Browse** every rank with a live preview.
* **Create** a new rank with the generator form, pick a style, icon and colours, press Generate (the same options as `/samsrank generate`).
* **Edit** any rank pixel by pixel.
* **Preview effects** - see each of the 17 Rank Effects on your tag before using it.

***

## Pixel Editor Tools

| Tool       | Purpose                                                |
| ---------- | ------------------------------------------------------ |
| **Pencil** | Paint single pixels with the primary/secondary colour. |
| **Eraser** | Clear pixels to transparency.                          |
| **Picker** | Sample a colour from the canvas.                       |
| **Fill**   | Flood fill connected areas of the same colour.         |
| **Select** | Mark a rectangular region to move or erase.            |
| **Move**   | Drag a selection to a new position.                    |
| **Shape**  | Draw perfect rectangles or straight lines.             |

***

## Saving and Rebuilding

When you save, SamsRank automatically:

1. Writes the PNG to `plugins/SamsRank/ranks/`.
2. Converts it so every platform's assets are updated.
3. Prompts you to reload the resource pack so you see the change in chat right away.

{% hint style="warning" %}
#### **Unsaved changes**

Leaving the editor with unsaved work shows a confirm popup, so you don't lose progress by accident.
{% endhint %}

***

## View-Only Mode

Give staff `samsrank.edit.view` (without `samsrank.edit`) and they can open the interface and look at every rank, but every change is blocked. A message tells them the editor is read-only when they open it.

***

## Tuning the Interface

The interface is pre-tuned for most setups. If it sits too high, too low or at the wrong size on yours, see UI settings. The main knob is `ui.rendering.hud-scale-divisor` - a **smaller** number makes the UI **bigger**.
