---
description: Integrate SamsHead into your own plugins!
icon: rectangle-api
---

# Developer API

## Developer API

SamsHead provides several utility classes to render player skins into colored text strings.

***

### Rendering an Avatar <a href="#rendering-an-avatar" id="rendering-an-avatar"></a>

To get the raw String containing colored PUA characters for an 8x8 head:

```java
// Get colors from cache (returns int[128] where 0-63 is face, 64-127 is head+hat)
int[] colors = samsHead.getSkinCache().getColors("PlayerName");

if (colors != null) {
    // Render to colored text using a specific size preset
    String avatar = AvatarRenderer.render(colors, RenderSize.NORMAL, RenderMode.HEAD);
}
```

***

### Rendering a Player Bust <a href="#fetching-skins-async" id="fetching-skins-async"></a>

For the full 32x32 player bust:

```java
int[] bustColors = samsHead.getSkinCache().getBustColors("PlayerName");

if (bustColors != null) {
    // Renders the full 32x32 grid
    String bust = BustRenderer.render(bustColors, BustSize.BUST_NORMAL);
}
```

***

### Fetching Skin Async <a href="#fetching-skins-async" id="fetching-skins-async"></a>

If a skin isn't in the cache, you should fetch it asynchronously. The `SkinFetcher` handles the Mojang API and SkinsRestorer lookups automatically.

```java
samsHead.getSkinFetcher().fetchAsync("PlayerName", 
    () -> {
        // Success callback: Skin is now in cache and DB
        plugin.getLogger().info("Skin is now ready!");
    }, 
    () -> {
        // Failure callback
        plugin.getLogger().warning("Could not fetch skin.");
    }
);
```

***

### Cache Managment <a href="#handling-sizes" id="handling-sizes"></a>

You can interact with the `SkinCache` directly to check status or evict players.

```java
SkinCache cache = samsHead.getSkinCache();

boolean isStale = cache.isStale("PlayerName", 86400);
boolean isFetching = cache.isFetching("PlayerName");

// Manually evict from memory (does not delete from SQLite DB)
cache.evict("PlayerName");
```
