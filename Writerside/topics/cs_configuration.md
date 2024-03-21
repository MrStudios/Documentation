# Configuration
In this document, we will explain what every field in ``config.yml`` file means, and how to configure that.

### Command Suggesting Map
In this field, you can specify which commands the player can see and use.

```yaml
command-suggesting-map:
  mrstudios.suggester.default:
    - msg
    - friend
    - party
  mrstudios.suggester.admin:
    - ban
    - mute
    - kick
```

<warning>
    <p>
        This field is a map with own structure, you must follow them to avoid issues, you can see structure scheme bellow.
        <code-block lang="yaml">
        command-suggesting-map:
          PERMISSION:
            - LIST_ENTRY
        </code-block><br>
        <code>PERMISSION</code> is permission that player must have to use that commands,
        <code>LIST_ENTRY</code> is command name that players with this permission can use.
    </p>
</warning>

### Can Not Use That Command Message 
In this field, you can specify a message that a player will receive when it doesn't have permission to use command.

```yaml
can-not-use-that-command-message: '<red>You can't use that command because you dont have permissions.'
```

<tip>
    <p>You can use <a href="https://docs.advntr.dev/minimessage/index.html">MiniMessage</a> component formatting.</p>
</tip>

