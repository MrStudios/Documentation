# Listen Events
In this document, you will find how to listen to events from `deathrun-api`.

### Make Listener
```Java
package com.example.extension.listeners;

import org.bukkit.event.Listener;
import org.bukkit.event.EventHandler;
import pl.mrstudios.deathrun.api.API;
import pl.mrstudios.deathrun.api.arena.event.arena.ArenaUserJoinedEvent;

public class ExampleListener implements Listener {

    private final API api;
    
    public ExampleListener(API api) {
        this.api = api;
    }

    @EventHandler
    public void onUserJoinedArena(ArenaUserJoinedEvent event) {
        event.getUser().asBukkit().sendMessage("You joined " + event.getArena().getName() + " arena.");
    }

}
```

### Register Listener
To register your listener, add the following lines to your code in ``JavaPlugin#onEnable()`` method.

```Java
this.getServer().getPluginManager().registerEvents(new ExampleListener(), this);
```

### Available Events
- ``ArenaGameStateChangeEvent`` **|** Event triggered after arena `GameState` changed.
- ``ArenaShutdownStartedEvent`` **|** Event triggered after arena enters shutdown phase.
- ``ArenaTrapActivateEvent`` **|** Event triggered when a user activates a trap.
- ``ArenaUserJoinedEvent`` **|** Event triggered when a user joined arena.
- ``ArenaUserLeftEvent`` **|** Event triggered when a user left arena.
- ``UserArenaCheckpointEvent`` **|** Event triggered when a user reached checkpoint.
- ``UserArenaDeathEvent`` **|** Event triggered when user die.
- ``UserArenaFinishedEvent`` **|** Event triggered when user finished arena.
- ``UserArenaRoleAssignedEvent`` **|** Event triggered when user has assigned role.
