# Listen Events
In this document, you will find how to listen to events from `antibot-api`.

### Make Listener
```Java
package com.example.extension.listeners;

import com.velocitypowered.api.event.Subscribe;
import org.jetbrains.annotations.NotNull;
import pl.mrstudios.antibot.api.event.PlayerChallengeCompletedEvent;

import static net.kyori.adventure.text.Component.text;

public class ExampleListener {

    @Subscribe
    public void onPlayerChallengeCompleted(
            @NotNull PlayerChallengeCompletedEvent event
    ) {
        event.getPlayer().sendMessage(text("onPlayerChallengeCompleted"));
    }

}

```

### Register Listener
To register your listener, add the following lines to your code in ``onProxyInitialization()`` method.

```Java
this.proxyServer.getEventManager().register(this, new ExampleListener());
```

### Available Events
PlayerChallengeCompletedEvent
{collapsible="true" default-state="collapsed"}
: Event triggered when player has completed a challenge.

PlayerChallengeFailedEvent
{collapsible="true" default-state="collapsed"}
: Event triggered when player has failed a challenge.

PlayerVerificationCompletedEvent
{collapsible="true" default-state="collapsed"}
: Event triggered when player completed the entire verification procedure.