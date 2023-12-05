# Make Extension
In this document, you will find how to make an extension using `deathrun-api`.

### Configuration
You must add ``DeathRun`` to ``softdepend`` in your ``plugin.yml``, otherwise any issues may be happening.

### Create Extension
```Java
package com.example.extension;

import org.bukkit.plugin.java.JavaPlugin;
import pl.mrstudios.deathrun.api.API;

public class ExampleExtension extends JavaPlugin {

    private API api;

    @Override
    public void onEnable() {

        /* Dependency Check */
        if (!getServer().getPluginManager().isPluginEnabled("DeathRun"))
            throw new RuntimeException("You must have 'DeathRun' plugin installed on your server.");

        /* Set API Instance */
        this.api = API.instance;

    }

}
```