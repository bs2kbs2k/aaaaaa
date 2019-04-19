# Ice Age

![Frozen fish](/static/mods/ice-age.jpg)

Aquatic creatures have been trapped in ice for a long time. Watch as they thaw out and come back to life!

## Try the code:

```blocks
let rando: Position = null
let topCorner: Position = null
let bottomCorner: Position = null
let layers: number[] = []
player.onItemInteracted(Item.Trident, function () {
    layers = [blocks.block(Block.Lava), blocks.block(Block.Glass), blocks.block(Block.Ice)]
    bottomCorner = positions.create(10, 0, 10).toWorld()
    topCorner = positions.add(
        bottomCorner,
        positions.create(10, 10, 10)
    )
    for (let index = 0; index <= layers.length - 1; index++) {
        blocks.fill(
            layers[index],
            positions.add(
                bottomCorner,
                positions.create(index, index, index)
            ),
            positions.add(
                topCorner,
                positions.create(0 - index, 0, 0 - index)
            ),
            FillOperation.Replace
        )
    }
    for (let i = 0; i < 20; i++) {
        rando = positions.random(
            positions.add(
                bottomCorner,
                positions.create(2, 2, 2)
            ),
            positions.add(
                topCorner,
                positions.create(-2, 0, -2)
            )
        )
        blocks.place(Block.Water, rando)
        mobs.spawn(AnimalMob.TropicalFish, rando)
    }
})
```