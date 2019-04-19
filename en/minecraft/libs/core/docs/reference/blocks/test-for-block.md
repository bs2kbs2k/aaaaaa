# test For Block

Test to see if a block at the chosen position is a certain type.

```sig
blocks.testForBlock(blocks.block(Block.Grass), positions.create(0, 0, 0));
```

## Parameters

* **block**: the type of the block to test for
* **pos**: the position, or coordinates, where you want to check for the block

## Example

This code warns the player if there is some lava two blocks above their head. If you see this warning, be careful when mining the block above you!

```blocks
player.onTravelled(TravelMethod.Walk, () => {
    if (blocks.testForBlock(blocks.block(Block.Lava), positions.create(0, 3, 0))) {
        player.say("Lava above!");
    }
});
```

## See Also

[`||blocks:test for blocks||`](/reference/test-for-blocks)