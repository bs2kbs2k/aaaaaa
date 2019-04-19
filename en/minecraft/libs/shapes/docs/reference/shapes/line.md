# line

Fill a line of blocks from one position to another.

```sig
shapes.line(
    blocks.block(Block.Grass),
    positions.create(0, 0, 0),
    positions.create(0, 0, 0)
);
```

## Parameters

* **p1**: the position of the start of the line
* **p2**: the position of the end of the line

## Example

Draw a diagonal line of gold from the player to a position `10` blocks to the East and `10` blocks to the North.

```blocks
player.onChat("diag", function () {
    shapes.line(
        blocks.block(Block.GoldBlock),
        positions.create(0, 1, 0),
        positions.create(10, 1, 10)
    )
})
```

## See also

[`||builder:builder line||`](/reference/builder/line)