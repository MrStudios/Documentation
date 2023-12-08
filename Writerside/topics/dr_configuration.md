# Configuration
In this document, we will explain what every field in ``config.yml`` file means, and how to configure that.

### Server
In this field, you can specify server for what players will be connected after an arena end or leave item or command usage.

```yaml
server: dr-lobby-1
```

### Arena Min Players
In this field, you can specify a minimum player amount needed to start an arena.

```yaml
arena-min-players: 5
```

### Arena Deaths Amount
In this field, you can specify the number of players with a `DEATH` role in an arena.

```yaml
arena-deaths-amount: 1
```

### Arena Game Time
In this field, you can specify how much time runners have to complete a map.

```yaml
arena-game-time: 600
```

<warning>
    <p>Value must be in seconds.</p>
</warning>

### Arena Pre Starting Time
In this field, you can specify how much time the arena will wait to start.

```yaml
arena-pre-starting-time: 30
```

<warning>
    <p>Value must be in seconds.</p>
</warning>

### Arena Starting Time
In this field, you can specify how much time runners must wait until a start barrier will be removed.

```yaml
arena-starting-time: 10
```

<warning>
    <p>Value must be in seconds.</p>
</warning>

### Arena Max Fall Distance
In this field, you can specify how many blocks a player can fall without dying.

```yaml
arena-max-fall-distance: 8
```

### Block Effects
In this field, you can specify what effects will be granted to player when he stands on this block.

```yaml
block-effects:
  - block: EMERALD_BLOCK
    effect: JUMP
    amplifier: 7
    duration: 1.5
  - block: REDSTONE_BLOCK
    effect: SPEED
    amplifier: 5
    duration: 1.5
```

<warning>
    <p>Field <code>block</code> must be an <a href="https://jd.papermc.io/paper/1.16/org/bukkit/Material.html">Material</a> enum value.</p>
</warning>
<warning>
    <p>Field <code>effect</code> must be an <a href="https://jd.papermc.io/paper/1.16/org/bukkit/potion/PotionEffectType.html">PotionEffectType</a> value.</p>
</warning>

### Boosters
In this field, you can specify boosters.

```yaml
boosters:
  - slot: 0
    power: 2.5
    delay: 10
    item:
      name: <green>Booster <gray>(Right Click)
      material: FEATHER
    delayItem:
      name: <red>Booster <gray>(<delay> seconds)
      material: FEATHER
    direction: FORWARD
    sound: ENTITY_BLAZE_AMBIENT
```

<warning>
    <p>Field <code>material</code> must be an <a href="https://jd.papermc.io/paper/1.16/org/bukkit/Material.html">Material</a> enum value.</p>
</warning>
<warning>
    <p>Field <code>direction</code> must be <code>FORWARD</code>, <code>BACKWARD</code>, <code>LEFT</code> or <code>RIGHT</code> value.</p>
</warning>
<warning>
    <p>Field <code>sound</code> must be an <a href="https://jd.papermc.io/paper/1.16/org/bukkit/Sound.html">Sound</a> enum value.</p>
</warning>
<tip>
    <p>
    If you want to use head texture, you can add <code>texture</code> field into <code>item</code> or <code>delayItem</code>, example is visible bellow.
    <code-block lang="yaml">
        boosters:
          - slot: 0
            power: 2.5
            delay: 10
            item:
              name: &#x3C;green&#x3E;Booster &#x3C;gray&#x3E;(Right Click)
              material: PLAYER_HEAD
              texture: eyJ0ZXh0dXJlcyI6eyJTS0lOIjp7InVybCI6Imh0dHA6Ly90ZXh0dXJlcy5taW5lY3JhZnQubmV0L3RleHR1cmUvYjIyMWRhNDQxOGJkM2JmYjQyZWI2NGQyYWI0MjljNjFkZWNiOGY0YmY3ZDRjZmI3N2ExNjJiZTNkY2IwYjkyNyJ9fX0=
            delayItem:
              name: &#x3C;red&#x3E;Booster &#x3C;gray&#x3E;(&#x3C;delay&#x3E; seconds)
              material: PLAYER_HEAD
              texture: eyJ0ZXh0dXJlcyI6eyJTS0lOIjp7InVybCI6Imh0dHA6Ly90ZXh0dXJlcy5taW5lY3JhZnQubmV0L3RleHR1cmUvNDVjNTg4YjllYzBhMDhhMzdlMDFhODA5ZWQwOTAzY2MzNGMzZTNmMTc2ZGM5MjIzMDQxN2RhOTNiOTQ4ZjE0OCJ9fX0=
            direction: FORWARD
            sound: ENTITY_BLAZE_AMBIENT
    </code-block>
    </p>
</tip>

### Arena Sound Pre Starting
In this field, you can specify what sound all players hear when an arena pre starting counting a milestone will be reached.

```yaml
arena-sound-pre-starting: BLOCK_NOTE_BLOCK_PLING
```

<warning>
    <p>Field must be an <a href="https://jd.papermc.io/paper/1.16/org/bukkit/Sound.html">Sound</a> enum value.</p>
</warning>

### Arena Sound Starting
In this field, you can specify what sound all players hear when an arena starting counting a milestone will be reached.

```yaml
arena-sound-starting: ENTITY_EXPERIENCE_ORB_PICKUP
```

<warning>
    <p>Field must be a <a href="https://jd.papermc.io/paper/1.16/org/bukkit/Sound.html">Sound</a> enum value.</p>
</warning>

### Arena Sound Started
In this field, you can specify what sound all players hear when an arena starts.

```yaml
arena-sound-started: ENTITY_ENDER_DRAGON_GROWL
```

<warning>
    <p>Field must be a <a href="https://jd.papermc.io/paper/1.16/org/bukkit/Sound.html">Sound</a> enum value.</p>
</warning>

### Arena Sound Checkpoint Reached
In this field, you can specify what sound player hears after reaching checkpoint.

```yaml
arena-sound-checkpoint-reached: ENTITY_EXPERIENCE_ORB_PICKUP
```

<warning>
    <p>Field must be a <a href="https://jd.papermc.io/paper/1.16/org/bukkit/Sound.html">Sound</a> enum value.</p>
</warning>

### Arena Sound Trap Delay
In this field, you can specify what sound player hears after trying to use a trap when it is on delay.

```yaml
arena-sound-trap-delay: ENTITY_VILLAGER_NO
```

<warning>
    <p>Field must be a <a href="https://jd.papermc.io/paper/1.16/org/bukkit/Sound.html">Sound</a> enum value.</p>
</warning>

### Arena Sound Player Death
In this field, you can specify what sound player hears after death.

```yaml
arena-sound-player-death: ENTITY_SKELETON_DEATH
```

<warning>
    <p>Field must be a <a href="https://jd.papermc.io/paper/1.16/org/bukkit/Sound.html">Sound</a> enum value.</p>
</warning>

