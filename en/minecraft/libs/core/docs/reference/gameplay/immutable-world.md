# immutable World

Control the ability for players to alter the world.

```sig
gameplay.immutableWorld(false);
```

## Parameters

* **enabled**: `true` if modifying the world is allowed, `false` if not allowed

## Example

Make the world immutable when someone tries to destroy stone blocks.

```blocks
blocks.onBlockBroken(blocks.block(Block.Stone), () => {
    player.say("No griefing!");
    gameplay.immutableWorld(true);
});
```