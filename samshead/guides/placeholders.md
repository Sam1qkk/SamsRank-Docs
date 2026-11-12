---
description: Using SamsHead with PlaceholderAPI
icon: code-simple
---

# Placeholders

## Placeholders

SamsHead provides highly flexible placeholders to render avatars and full player busts anywhere text is supported.

***

## Avatar Head Syntax

The format follows: `%samshead_avatar_<size>[_layer][_border_RRGGBB][_<player>]%`.

#### 1. Size Presets <a href="#id-1-size-presets" id="id-1-size-presets"></a>

Choose from `small`, `medium`, `normal`, `large`, or `giant`.

#### 2. Layers (Optional) <a href="#id-2-layers-optional" id="id-2-layers-optional"></a>

* `face`: Only the base skin layer.
* `head`: Skin + Hat/Overlay layer (Default).

#### 3. Framed Avatars (Borders) <a href="#id-2-layers-optional" id="id-2-layers-optional"></a>

You can now add a 1-pixel colored border around any avatar. This uses a specialized 10x10 glyph set to ensure the head remains clean.

* Syntax: `border_<RRGGBB>`
* Example: `%samshead_avatar_medium_border_ff0000%` (Red border)

#### 4. Target Player (Optional) <a href="#id-3-target-player-optional" id="id-3-target-player-optional"></a>

If omitted, the placeholder targets the player viewing it.

{% tabs %}
{% tab title="Personalised" %}
`%samshead_avatar_medium%` Displays the viewer's own head (default layer).
{% endtab %}

{% tab title="Specific Player" %}
`%samshead_avatar_normal_Notch%` Displays Notch's head.
{% endtab %}

{% tab title="Borders & Layers" %}
`%samshead_avatar_large_head_border_ffd700_Notch%` Displays Notch's head with a gold border.
{% endtab %}

{% tab title="Layer Override" %}
`%samshead_avatar_giant_face_Sam1qk_%` Displays Sam1qk\_'s face only (no hat) in giant size.
{% endtab %}
{% endtabs %}

***

## Player Bust Syntax

Busts render a 32×32 Minecraft-style display including the head, body, and arms.

{% hint style="danger" %}
#### Scoreboard/TAB Safety

Bust placeholders are **NOT** safe for Scoreboards, TAB rows, or Nametags. They generate long text strings that can cause client kicks due to packet length limits. Use them in Chat, Holograms, or GUIs only.
{% endhint %}

Format: `%samshead_bust_<size>_<player>%`

#### Available Bust Sizes <a href="#id-1-size-presets" id="id-1-size-presets"></a>

| Preset | Pixel Size |
| ------ | ---------- |
| small  | 1          |
| medium | 2          |
| normal | 2          |
| large  | 3          |
| giant  | 4          |

{% hint style="success" %}
#### SkinsRestorer

SamsHead is fully compatible with SkinsRestorer. It will automatically detect skin changes and update the rendered avatar instantly.
{% endhint %}

***

## Nested placeholders (dynamic names)

PlaceholderAPI does not expand a `%...%` inside another `%...%`. To feed one placeholder's output (for example a top-money leaderboard name) into an avatar, wrap the inner placeholder in **curly braces**:

```
%samshead_avatar_small_{perfranknpcs_money_alltime_1_name}%
%samshead_bust_normal_{perfranknpcs_money_alltime_2_name}%
```

SamsHead resolves the inner `{placeholder}` first, then renders that player's avatar.. perfect for leaderboards where the name changes.

{% hint style="info" %}
#### Good to know

Pick a leaderboard placeholder that returns **just the username** (usually the `..._name` variant). If it returns a prefixed/coloured name with spaces, SamsHead can't match a player from it.
{% endhint %}
