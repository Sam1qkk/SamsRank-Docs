---
description: How to use the built-in rank manager and pixel editor
icon: computer-speaker
---

# In-Game Editor

In-Game Interface


SamsRank features a revolutionary UI built entirely from display entities. This allows you to manage, design, and edit your rank tags without ever leaving the game or touching a configuration file.

{% hint style="info" %}
#### How to Open?

Run `/samsrank` or `/samsrank menu` to open the manager. To jump straight into editing a specific rank, use `/samsrank edit <rankname>`.
{% endhint %}

***

## Controls

Instead of a traditional inventory menu, the SamsRank UI is projected in front of your camera.

* **Movement**: Move with your mouse to move the cursor. The cursor sensitivity can be adjusted in the `config.yml`.
* **Interaction**:
  * **Left Click**: Select tools, press buttons, or paint pixels.
  * **Right Click**: Use tool actions (like zooming out or painting with the secondary color).
  * **Scroll Wheel**: Zoom in/out on or cycle through effect presets.
  * **Sneak (Shift)**: Hold while scrolling to change your brush size.
* **Closing**: Press **F** (Swap hands) to close the interface at any time.

***

## Pixel Editor Tools

The editor on the left provides tools for pixel art:

|    Tool    |                       Purpose                      |
| :--------: | :------------------------------------------------: |
| **Pencil** | Paint single pixels with primary/secondary colors. |
| **Eraser** |            Clear pixels to transparency.           |
| **Picker** |      Sample a color directly from the editor.      |
|  **Fill**  |    Flood fill connected areas of the same color.   |
| **Select** | Define a rectangular region for moving or erasing. |
|  **Move**  |         Drag a selection to a new position.        |
|  **Shape** |     Draw perfect rectangles or straight lines.     |

***

## Saving and Rebuilding

When you save your changes in the editor, SamsRank automatically:

1. Overwrites the source PNG in `plugins/SamsRank/ranks/`.
2. Triggers a `/samsrank convert` to update all platform assets.
3. Prompts you to reload the resource pack so you can see the changes in chat immediately.

{% hint style="warning" %}
#### Unsaved Changes

If you try to leave the editor with unsaved work, a confirm popup will appear to prevent accidental loss of progress.
{% endhint %}
