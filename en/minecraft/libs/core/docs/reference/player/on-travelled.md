# on Travelled

Runs code when the current player travels in a certain way.

```sig
player.onTravelled(TravelMethod.Walk, () => {

});
```

## Parameters

- **method**: the travel method. The methods you can use are: > `walk`, `swim water`, `fall`, `climb`, `swim lava`, `fly`, `riding`, `sneak`, `sprint`, `bounce`
- **handler**: code to run when the player travels

## Example

Leave a trail of flowers behind when the player walks around:

```blocks
player.onTravelled(TravelMethod.Walk, () => {
    blocks.place(blocks.block(Block.YellowFlower), positions.create(0, 0, 0));
});
```