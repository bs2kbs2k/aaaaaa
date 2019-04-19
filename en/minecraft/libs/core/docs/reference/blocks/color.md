# color

Return one of the colors from all of the known block colors. Wool and concrete can have multiple colors so this is used to color those blocks.

```sig
blocks.color(BlockColor.White);
```

## Parameters

* **color** the color

## Example

Use the `color` block to place yellow wool near the player.

```blocks
blocks.place(blocks.colorToBlock(ColoredBlock.Wool, blocks.color(BlockColor.Yellow)), positions.create(1, 0, 0));
```

## See Also

[`||blocks:color to block||`](/reference/blocks/color-to-block)