# test For Blocks

Test to see if two cubic regions contain the same blocks.

```sig
blocks.testForBlocks(
    positions.create(0, 0, 0),
    positions.create(0, 0, 0),
    positions.create(0, 0, 0),
    TestForBlocksMask.All
);
```

## Parameters

* **begin**: the first corner of the cubic region
* **end**: the opposite corner of the cubic region
* **destination**: the first corner of the destination region
* **mask**: how to handle air blocks: 
    * `all`: all blocks must match for the test to be true, including air blocks
    * `masked`: the comparison ignores air blocks in the source region; the destination region can have any block in those positions

## Example

See if the ceiling above the current player is made of the same blocks just below the current player's feet. If so, display a message.

```blocks
player.onTravelled(TravelMethod.Walk, () => {
    if (blocks.testForBlocks(
        positions.create(-1, -1, -1),
        positions.create(1, -1, 1),
        positions.create(-1, 2, -1),
        TestForBlocksMask.All
    )) {
        player.say("Same blocks!");
    }
});
```

## See Also

[`||blocks:test for block||`](/reference/test-for-block)