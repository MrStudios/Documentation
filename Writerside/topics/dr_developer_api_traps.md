# Make Traps
In this document, you will find how to make an own traps using `deathrun-api`.

### Make Trap
```Java
package com.example.extension.listeners;

import org.bukkit.Location;
import org.bukkit.Material;
import org.jetbrains.annotations.NotNull;
import org.jetbrains.annotations.Nullable;
import pl.mrstudios.deathrun.api.arena.trap.ITrap;

import java.time.Duration;
import java.util.List;

public class ExampleTrap implements ITrap {

    private Location button;
    private List<Location> locations;
    private Material extra;

    @Override
    public void start() {
        this.locations.forEach((location) -> location.getBlock().setType(this.extra));
    }

    @Override
    public void end() {
        this.locations.forEach((location) -> location.getBlock().setType(Material.AIR));
    }

    @Override
    public @NotNull List<Location> filter(@NotNull List<Location> list, @Nullable Object... objects) {

        if (objects == null || objects.length == 0)
            return list;

        if (!(objects[0] instanceof Material material))
            return list;

        return list.stream()
                .filter((location) -> location.getBlock().getType() == material)
                .toList();

    }

    @Override
    public void setExtra(@Nullable Object... objects) {

        if (objects == null || objects.length == 0)
            return;

        if (objects[0] instanceof Material material)
            this.extra = material;

    }

    @Override
    public @NotNull Duration getDuration() {
        return Duration.ofSeconds(3);
    }

    @Override
    public @NotNull Location getButton() {
        return this.button;
    }

    @Override
    public void setButton(@NotNull Location location) {
        this.button = button;
    }

    @Override
    public @NotNull List<Location> getLocations() {
        return this.locations;
    }

    @Override
    public void setLocations(@NotNull List<Location> list) {
        this.locations = list;
    }

}

```

### Method Explain
- `ITrap#start()` **|** Triggers on trap start.
- `ITrap#end()` **|** Triggers on trap end.
- `ITrap#filter()` **|** Triggers on set up a trap, return list that will be saved in `map.yml` file.
- `ITrap#setExtra()` **|** Triggers on set up a trap, provides `material` argument if that exists.
- `ITrap#getDuration()` **|** Returns amount of time that trap is running in a `Duration` object.

### Trap Registration
To register your trap, add the following lines to your code in ``JavaPlugin#onEnable()`` method.

```Java
this.api.getTrapRegistry().register("example", ExampleTrap.class);
```
