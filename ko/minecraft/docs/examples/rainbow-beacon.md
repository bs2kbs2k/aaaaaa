# 무지개 단추

![무지개 단추](/static/mods/rainbow-beacon.jpg)

Send your your colors up! Here's a beacon with the colors of the rainbow.

## Try the code:

```blocks
let location: Position = null
let rainbow: number[] = []
player.onChat("beacon", function () {
    location = positions.add(
    player.position(),
    positions.create(1, 0, 0)
    )
    for (let i = 0; i < 10; i++) {
        for (let value of rainbow) {
            blocks.place(value, location)
            location = positions.add(
            location,
            positions.create(0, 1, 0)
            )
        }
    }
})
rainbow = [
    blocks.block(Block.RedConcrete), blocks.block(Block.OrangeConcrete),
    blocks.block(Block.YellowConcrete), blocks.block(Block.LimeConcrete),
    blocks.block(Block.GreenConcrete), blocks.block(Block.LightBlueConcrete),
    blocks.block(Block.BlueConcrete), blocks.block(Block.MagentaConcrete),
    blocks.block(Block.PurpleConcrete), blocks.block(Block.PinkConcrete)
]
```