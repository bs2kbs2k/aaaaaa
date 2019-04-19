# trace Path

Trace the path traveled from the last marked position with the selected block type.

You can trace the [`||builder:teleport to||`](/reference/builder/teleport-to), [`||builder:move||`](/reference/builder/move), and [`||builder:shift||`](/reference/builder/shift) builder actions with `||builder:trace path||`.

```sig
builder.tracePath(blocks.block(Block.Grass));
```

## Parameters

* **block**: the type of block used to trace the path

## Example

Make the builder move randomly around the player. Trace where the builder goes with gold blocks.

```blocks
builder.teleportTo(positions.create(0, 2, 0));
builder.mark();
builder.move(SixDirection.Forward, Math.randomRange(0, 11));
builder.move(SixDirection.Left, Math.randomRange(0, 11));
builder.move(SixDirection.Up, Math.randomRange(0, 11));
builder.tracePath(blocks.block(Block.GoldBlock));
```

## See Also

Here's an example project that uses the builder: [Build a house](/examples/house-builder).