# Configuration
In this document, we will explain what every field in ``config.yml`` file means, and how to configure that.

### Cache Clear Interval
In this field, you can specify how long player verification will be valid.

```yaml
cache-clear-interval: 300
```

### Verification Procedure Timeout
In this field, you can specify how many times a player has to complete verification procedure.

```yaml
verification-procedure-timeout: 60
```

### Verification Challenge Pool
In this field, you can add, remove or modify an interactive challenge in pool.

```yaml
verification-challenge-pool:
  - type: COLLECT_ITEMS
    translation: Collect {amount}x Iron Ore.
    extra:
      gather: IRON_ORE
  - type: COLLECT_ITEMS
    translation: Collect {amount}x Diamond.
    extra:
      gather: DIAMOND_ORE
  - type: COLLECT_ITEMS
    translation: Collect {amount}x Coal Ore.
    extra:
      gather: COAL_ORE
  - type: COLLECT_ITEMS
    translation: Collect {amount}x Logs.
    extra:
      gather: LOG
  - type: CLICK_BLOCK
    translation: Use anvil {times} times.
    extra:
      click: ANVIL
  - type: CLICK_BLOCK
    translation: Use crafting table {times} times.
    extra:
      click: CRAFTING_TABLE
  - type: CLICK_BLOCK
    translation: Use furnace {times} times.
    extra:
      click: FURNACE
  - type: SNEAK
    translation: Sneak {times} times.
  - type: WALK_TO
    translation: Follow particles displayed above you.
  - type: EAT_FOOD
    translation: Eat until your food bar is full.
```

<warning>
    <p>
        This field is a list with own structure, you must follow them to avoid issues, you can see structure scheme bellow.
        <code-block lang="yaml">
        verification-challenge-pool:
          - type: CHALLENGE
            translation: TRANSLATION
            extra: EXTRA
        </code-block><br>
        <code>CHALLENGE</code> must be one of <code>COLLECT_ITEMS</code>, <code>CLICK_BLOCK</code>, <code>SNEAK</code>, <code>WALK_TO</code> or <code>EAT_FOOD</code>.<br>
        <code>TRANSLATION</code> is replacement for <code>{content}</code> placeholder.<br>
        <code>EXTRA</code> is optional map with values that is used by <code>CHALLENGE</code>.
        <ul>
            <li>For <code>COLLECT_ITEMS</code> available is <code>gather</code> that must be element of <code>Item</code> enum.</li>
            <li>For <code>CLICK_BLOCK</code> available is <code>click</code> that must be element of <code>Block</code> enum.</li>
            <li>For <code>WALK_TO</code> available is <code>red</code>, <code>green</code>, <code>blue</code> and <code>scale</code> that are float for dust particle.</li>
            <li>For <code>EAT_FOOD</code> extra parameters are not available.</li>
        </ul>
    </p>
</warning>

### Verification Procedure
In this field, you can create a managed procedure that will be different for each player.

```yaml
verification-procedure:
  - trigger: BRAND_CHECK
  - trigger: SETTINGS_CHECK
  - trigger: GRAVITY_CHECK
    expression: onlineMode
  - trigger: CHALLENGE
    expression: '!onlineMode || !brandCheck || !settingsCheck'
```

<warning>
    <p>
        This field is a list with own structure, you must follow them to avoid issues, you can see structure scheme bellow.
        <code-block lang="yaml">
        verification-procedure:
          - trigger: TRIGGER
            expression: EXPRESSION
        </code-block><br>
        <code>TRIGGER</code> is one of available options
        <ul>
            <li><code>BRAND_CHECK</code> is check that require client to send <code>minecraft:brand</code> payload.</li>
            <li><code>SETTINGS_CHECK</code> is check that require client to send packet with settings.</li>
            <li><code>GRAVITY_CHECK</code> is a basic client gravity check. <i>(if client is falling correctly)</i></li>
            <li><code>CHALLENGE</code> is a most advanced check that requires interaction from a client.</li>
        </ul><br>
        <code>EXPRESSION</code> is boolean expression that have available parameters<br>
        - onlineMode <i>(boolean)</i><br>
        - protocol <i>(integer)</i><br>
        - brandCheck <i>(boolean)</i><br>
        - settingsCheck <i>(boolean)</i><br>
        <br>
        Example Expressions:
        <code-block lang="java">
        onlineMode
        </code-block>
        <code-block lang="java">
        !onlineMode && !brandCheck && !settingsCheck
        </code-block>
        <code-block lang="java">
        (protocol >= 767 && !onlineMode) || !settingsCheck || !brandCheck
        </code-block>
    </p>
</warning>


