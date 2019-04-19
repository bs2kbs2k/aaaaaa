# Walk on Water

![Walking on water](/static/mods/walk-on-water.jpg)

Don't get your toes wet!

## Try the code:

```blocks
player.onTravelled(TravelMethod.SwimWater, function () {
    blocks.fill(
    blocks.block(Block.Ice),
    positions.create(-1, -1, -1),
    positions.create(1, -1, 1),
    FillOperation.Replace
    )
})
```