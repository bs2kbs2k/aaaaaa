# Blocks

The **blocks** that make the world of Minecraft can be manipulated with code: place, fill, clone, replace are all possible with the blocks below.

### ~ hint

**[Learn about positions](/reference/positions)** as most blocks commands use them.

### ~

### Types

A block type is represented by a number, composed of its ID value and optional data values. Various helpers like `||blocks:block||` or `||blocks:blockWithData||` are there to help you craft the block you want.

## Reference

```cards
blocks.place(blocks.block(Block.Grass), positions.create(0, 0, 0));
blocks.fill(
    blocks.block(Block.Grass),
    positions.create(0, 0, 0),
    positions.create(0, 0, 0),
    FillOperation.Replace
);
blocks.onBlockPlaced(blocks.block(Block.Grass), () => {

});
blocks.onBlockBroken(blocks.block(Block.Grass), () => {

});
blocks.testForBlock(blocks.block(Block.Grass), positions.create(0, 0, 0));
blocks.block(Block.Grass);
blocks.item(Item.IronShovel);
```

## Volumes

```cards
blocks.print(
    "HELLO",
    blocks.block(Block.Grass),
    positions.create(0, 0, 0),
    CompassDirection.West
);
blocks.replace(
    blocks.block(Block.Grass),
    blocks.block(Block.Grass),
    positions.create(0, 0, 0),
    positions.create(0, 0, 0)
);
blocks.clone(
    positions.create(0, 0, 0),
    positions.create(0, 0, 0),
    positions.create(0, 0, 0),
    CloneMask.Replace,
    CloneMode.Normal
);
blocks.cloneFiltered(
    positions.create(0, 0, 0),
    positions.create(0, 0, 0),
    positions.create(0, 0, 0),
    blocks.block(Block.Grass),
    CloneMode.Normal
);
```

## Advanced

```cards
blocks.blockWithData(blocks.block(Block.Grass), 0);
blocks.blockById(0);
blocks.blockByName("stone");
blocks.repeater(CompassDirection.West, 1);
blocks.comparator(CompassDirection.West, ComparatorMode.Compare);
blocks.lever(LeverPosition.BlockBottomEastWhenOff);
```