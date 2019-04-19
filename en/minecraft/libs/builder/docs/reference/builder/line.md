# line

Create a **line** of blocks from the builder's mark to the current position.

You chose the type of block to make the line with. The wall starts at the last position **mark** and goes to the builder's current position.

```sig
builder.line(blocks.block(Block.Grass));
```

## Parameters

* **block**: the type of block to use to build line

## Example

Use the builder to draw a diagonal line of diamond blocks near the player.

```blocks
builder.teleportTo(positions.create(0, 2, 0));
builder.shift(-20, -2, -20);
builder.line(blocks.block(Block.DiamondBlock));
```

## See Also

[`||builder:raise wall||`](/reference/builder/raise-wall), [`||builder:trace path||`](/reference/builder/trace-path)

Here's an example project that uses the builder: [Build a house](/examples/house-builder).