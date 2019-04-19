# clone Filtered

Clone, make a copy of a cubic region from one location into a another location. But, only clone if the blocks in the region match a certain block type.

```sig
blocks.cloneFiltered(
    positions.create(0, 0, 0),
    positions.create(0, 0, 0),
    positions.create(0, 0, 0),
    blocks.block(Block.Grass),
    CloneMode.Normal
);
```

## Parameters

* **begin**: the first corner of the cubic region
* **end**: the opposite corner of the cubic region
* **destination**: the first corner of the destination region
* **block**: the block type to look for when cloning
* **mode**: how to handle the cloned region: > * `normal`: the cloned region is not changed; if the destination region overlaps it, then the clone operation does nothing > * `force`: the cloned region is overwritten by the destination region if the two regions overlap > * `move`: the cloned region is replaced with air after the clone operation

The clone command in the [Minecraft wiki](http://minecraft.gamepedia.com/Commands#clone) describes how cloning works.

## Example

This code moves gold ore that is under the player to a region above the player. This makes the ore easier to see and mine.

```blocks
player.onTravelled(TravelMethod.Walk, () => {
    blocks.cloneFiltered(
        positions.create(-2, -3, -2),
        positions.create(2, 0, 2),
        positions.create(-2, 3, -2),
        blocks.block(Block.GoldOre),
        CloneMode.Move
    );
});
```

## See Also

[`||blocks:clone||`](/reference/blocks/clone)