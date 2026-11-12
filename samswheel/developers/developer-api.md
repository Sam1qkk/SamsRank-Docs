---
description: Hook into SamsWheel from your own plugin!
icon: rectangle-api
---

# Developer API

## Overview

SamsWheel exposes a small public API under `com.samscreations.samswheel.api`:

* **`SamsWheelAPI`** -> a facade for wheels, spinning, tickets, free spins, cooldowns and stats.
* **Three events** under `com.samscreations.samswheel.api.event` for reacting to (and controlling) spins.

{% hint style="info" %}
#### API Events

`Wheel` and `Reward` (in `com.samscreations.samswheel.wheel`) are passed to the API and events, so you can read a wheel's id, display name, rewards and settings directly.
{% endhint %}

***

## Adding the Dependency

Declare SamsWheel as a soft dependency in your `plugin.yml`:

```javascript
softdepend: [SamsWheel]
```

Then compile against the SamsWheel jar. Drop `SamsWheel-x.y.z.jar` into a `libs/` folder and reference it (it's provided at runtime, so use `compileOnly`):

```javascript
dependencies {
    compileOnly files("libs/SamsWheel-1.4.0.jar")
}
```

```javascript
<dependency>
    <groupId>com.samscreations</groupId>
    <artifactId>samswheel</artifactId>
    <version>1.2.0</version>
    <scope>system</scope>
    <systemPath>${project.basedir}/libs/SamsWheel-1.4.0.jar</systemPath>
</dependency>
```

***

## Getting the API

Obtain the facade after SamsWheel has enabled:

```java
import com.samscreations.samswheel.api.SamsWheelAPI;

SamsWheelAPI api = SamsWheelAPI.get(); // throws IllegalStateException if SamsWheel isn't enabled
```

{% hint style="warning" %}
#### Important

Call it only once SamsWheel is enabled (e.g. from your own `onEnable`, after a soft-depend load, or lazily when you need it) not from a static initializer
{% endhint %}

***

## Events

All three live in `com.samscreations.samswheel.api.event` and carry the `Player`, `Wheel` and chosen `Reward`.

| Event                    | When it fires                                                                                                                                               | Cancellable |
| ------------------------ | ----------------------------------------------------------------------------------------------------------------------------------------------------------- | ----------- |
| `WheelSpinStartEvent`    | After every check passes and the winning reward is chosen, **before cost is taken**. Cancelling aborts the spin cleanly with nothing consumed.              | ✅           |
| `WheelRewardWinEvent`    | The moment a reward is about to be handed out. Cancelling **suppresses the built-in delivery** (commands, messages, sounds) so you can pay it out yourself. | ✅           |
| `WheelSpinCompleteEvent` | Once the animation finishes and the reward is delivered. Informational.                                                                                     | ❌           |

***

## Example listener

```java
import com.samscreations.samswheel.api.event.WheelRewardWinEvent;
import org.bukkit.event.EventHandler;
import org.bukkit.event.Listener;

public class MyListener implements Listener {

    @EventHandler
    public void onWin(WheelRewardWinEvent event) {
        var player = event.getPlayer();
        var wheel  = event.getWheel();
        var reward = event.getReward();

        player.sendMessage(player.getName() + " won " + reward.getDisplayName()
                + " on " + wheel.getDisplayName());

        // Take over the payout entirely:
        // event.setCancelled(true);
    }
}
```

***

### API Reference

#### Wheels

```java
Wheel wheel            = api.getWheel("daily");
Collection<Wheel> all  = api.getWheels();
Wheel created          = api.createWheel("event", location); // null if the id exists
boolean removed        = api.removeWheel("event");
```

#### Reading & changing a wheel's settings

`Wheel` and `Reward` expose public getters/setters for every editor setting, so you can inspect or tweak a wheel from code.

```java
Wheel wheel = api.getWheel("daily");

// Read
boolean idle   = wheel.isIdleSpinEnabled();
double  rpm    = wheel.getIdleSpinSpeed();
String  nameBg = wheel.getRewardNameBackground(); // "default" / "none" / ARGB hex
int     rockets= wheel.getFireworkCount();

// Change (call wheel.save() to persist, and respawn via /samswheel reload to show it)
wheel.setIdleSpinEnabled(true);
wheel.setIdleSpinSpeed(3.0);
wheel.save();

// Rewards and their icons
for (Reward reward : wheel.activeRewards()) {
    ItemSpec icon = reward.getIcon(); // material, amount, name, lore, snapshot, ...
}
```

#### Spinning

```java
boolean started = api.startSpin(player, "daily"); // by id
boolean ok      = api.startSpin(player, wheel);    // by object
```

Returns `false` if the wheel doesn't exist or the spin can't start (e.g. cost not met, on cooldown, already spinning).

#### Tickets & Free Spins

```java
ItemStack ticket = api.createTicket("daily", 1);   // a physical ticket item
boolean gave     = api.giveTicket(player, "daily", 1);

// Virtual tickets: a stored per-wheel balance,
// spent when the wheel's cost is TICKET and no physical ticket is held.
api.giveVirtualTickets(uuid, "daily", 3);
api.takeVirtualTickets(uuid, "daily", 1);
int vtickets = api.getVirtualTickets(uuid, "daily");

api.giveFreeSpins(uuid, "daily", 3);
api.takeFreeSpins(uuid, "daily", 1);
int spins = api.getFreeSpins(uuid, "daily");
```

#### Cooldowns

```java
long remainingMs = api.remainingCooldownMillis(uuid, "daily");
api.resetCooldown(uuid, "daily");
```

#### Statistics

Statistics read from the database and return a `CompletableFuture`:

```java
api.totalSpins().thenAccept(count -> ...);
api.totalRewards().thenAccept(count -> ...);
api.wheelSpins("daily").thenAccept(count -> ...);
api.playerSpins(uuid).thenAccept(count -> ...);
```
