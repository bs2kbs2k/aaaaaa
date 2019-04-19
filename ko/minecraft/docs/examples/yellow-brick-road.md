# Yellow brick road

![Yellow brick road](/static/mods/yellow-brick-road.jpg)

Make a path of gold wherever you go.

## Try the code:

```blocks
player.onTravelled(TravelMethod.Walk, function () {
    blocks.place(blocks.block(Block.GoldBlock), positions.create(0, -1, 0))
})
player.onChat("road", function () {
    blocks.fill(
    blocks.block(Block.GoldBlock),
    positions.create(-1, -1, -1),
    positions.create(1, -1, 1),
    FillOperation.Replace
    )
})
```