# 집 만들기

![House made from blocks](/static/mods/house.jpg)

Let's build a house! The [builder](/reference/builder) gets busy in this example.

## Try the code:

```blocks
let roofLayers = 0
player.onChat("house", function (width, height) {
    builder.teleportTo(positions.create(0, -1, -5))
    for (let i = 0; i <= height - 1; i++) {
        builder.move(SixDirection.Up, 1)
        builder.mark()
        for (let j = 0; j <= 3; j++) {
            builder.move(SixDirection.Forward, width - 1)
            builder.turn(TurnDirection.Left)
        }
        builder.tracePath(blocks.block(Block.Stone))
    }
    builder.shift(-1, 1, -1)
    if (width % 2 == 0) {
        roofLayers = width / 2 - 1
    } else {
        roofLayers = width / 2
    }
    for (let layer = 0; layer <= roofLayers + 1; layer++) {
        builder.mark()
        for (let k = 0; k <= 3; k++) {
            builder.move(SixDirection.Forward, width + 1 - layer * 2)
            builder.turn(TurnDirection.Left)
        }
        builder.tracePath(blocks.block(Block.PlanksOak))
        builder.shift(1, 1, 1)
    }
    builder.move(SixDirection.Down, roofLayers + height + 2)
    builder.mark()
    builder.move(SixDirection.Forward, width / 2 + 1)
    builder.move(SixDirection.Up, 1)
    builder.fill(blocks.block(Block.Air))
    builder.shift(width * -1 + 1, 0, width / 2 - 1)
    builder.place(blocks.block(Block.Glass))
    builder.move(SixDirection.Right, width - 1)
    builder.place(blocks.block(Block.Glass))
})
```

```package
빌더
```