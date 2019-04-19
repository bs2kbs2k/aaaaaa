# execute Detect

Execute a command as other targets, but only if a certain block type is detected at some position.

```sig
mobs.executeDetect(
    blocks.block(Block.Grass),
    positions.create(0, 0, 0),
    "say Hi!"
);
```

This will execute a command just as if you or other players typed a command in the chat window. This command will execute at the position you choose.

## Parameters

* **detectBlock**: the block type to test for
* **detectPosition**: the position where you want to detect the block
* **command**: the full command you want to run if the right block type is detected.

## Example

When the player walks on diamond ore, all the players will display a happy comment in the chat.

```blocks
player.onTravelled(TravelMethod.Walk, () => {
    mobs.executeDetect(
        blocks.block(Block.DiamondOre),
        positions.create(0, -2, 0),
        "say Yay, diamond!"
    );
});
```

## See also

[`||mobs:execute||`](/reference/mobs/execute)