# replace

Replace all the blocks of a certain type inside the specified region with a new block type

```sig
blocks.replace(
    blocks.block(Block.Grass),
    blocks.block(Block.Grass),
    positions.create(0, 0, 0),
    positions.create(0, 0, 0)
);
```

## Parameters

* **newblock**: the new block type that replaces existing blocks
* **oldblock**: the block type that is replaced by the new block type
* **from**: the first corner of the cubic region
* **to**: the opposite corner of the cubic region

## Example

Replace coal ore with shiny diamond ore around the player!

```blocks
player.onTravelled(TravelMethod.Walk, () => {
    blocks.replace(
        blocks.block(Block.DiamondOre),
        blocks.block(Block.CoalOre),
        positions.create(-2, -2, -2),
        positions.create(2, 2, 2)
    );
});
```