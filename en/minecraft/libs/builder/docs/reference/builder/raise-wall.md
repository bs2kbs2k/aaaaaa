# raise Wall

Raise a wall of blocks from the builder's mark to the current position.

You chose the type of block to use and how many blocks high to raise the wall. The wall starts at the last position **mark** and goes to the builder's current position.

```sig
builder.raiseWall(blocks.block(Block.Grass), 5);
```

## Parameters

* **block**: the type of block to use for the wall
* **height**: the height of the wall in blocks, such as: 5

## Example

Use the builder to create a diagonal wall near the player.

```blocks
builder.teleportTo(positions.create(1, 0, 0));
builder.mark();
builder.teleportTo(positions.create(10, 0, 10));
builder.raiseWall(blocks.block(Block.Stone), 3);
```

## See Also

[`||builder:line||`](/reference/builder/line)

Here's an example project that uses the builder: [Build a house](/examples/house-builder).