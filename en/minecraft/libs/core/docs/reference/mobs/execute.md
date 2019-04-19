# execute

Execute a command as other targets or yourself.

This will execute a command just as if you or other players typed a command in the chat window. This command will execute at the position you choose.

```sig
mobs.execute(
    mobs.target(TargetSelectorKind.LocalPlayer),
    positions.create(0, 0, 0),
    ""
);
```

## Parameters

* **target**: a target selector that determines which entities will execute the command
* **position**: the coordinates where the command runs at
* **command**: the full command you want the selected targets to execute

## Example

When the player types "ping" in the chat, all players reply with "pong".

```blocks
player.onChat("ping", function () {
    mobs.execute(
        mobs.target(TargetSelectorKind.AllPlayers),
        positions.create(0, 0, 0),
        "say pong"
    );
});
```

## See also

[`||mobs:execute detect||`](/reference/mobs/execute-detect)