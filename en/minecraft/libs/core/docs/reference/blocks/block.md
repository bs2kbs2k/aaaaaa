# block

A block item from the game.

```sig
blocks.block(Block.Grass);
```

## Parameters

* **block**: the block

## Example

Place a block of diamond near the player.

```blocks
blocks.place(blocks.block(Block.DiamondBlock), positions.create(1, 0, 0));
```

## See Also

[`||blocks:item||`](/reference/blocks/item)