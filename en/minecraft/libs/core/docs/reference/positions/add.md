# add

Add two positions together and create a new position.

```sig
positions.add(
    positions.create(0, 0, 0),
    positions.create(0, 0, 0)
);
```

The two positions can be any type: ***relative*** or ***world***. But, the ***sum*** (the result of the two positions added together) has the same type as the first position. Make sure the type of the first position is the type you want your `||positions:add||` to make.

This code:

```block
let relPosition = positions.add(
    positions.create(2, 2, 2),
    positions.createWorld(3, 3, 3)
)
```

will create the ***relative*** position **(~5, ~5, ~5)**. Notice that the second position is a ***world*** position.

This code shows the opposite case:

```block
let worldPosition = positions.add(
    positions.createWorld(2, 2, 2),
    positions.create(3, 3, 3)
)
```

It will create the ***world*** position **(5, 5, 5)**. Notice that the second position is ***relative*** to the player.

## Parameters

* **p1**: the first position, has the same type as the result you want
* **p2**: the second position, added to the first position

## Example

Place a block of gold above the player's head by adding some extra height to the player's world position. This uses a relative position as the second position to add 2 blocks to the player's position.

```blocks
blocks.place(blocks.block(Block.GoldBlock), positions.add(
    player.position(),
    positions.create(0, 2, 0)
));
```