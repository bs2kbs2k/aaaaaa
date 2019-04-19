# Build Wall

![A wall with stone blocks](/static/mods/builder-wall.jpg)

Build a stone wall straight up.

## Try the code:

```blocks
player.onChat("wall", function () {
    for (let i = 0; i < 10; i++) {
        builder.move(SixDirection.Forward, 5)
        builder.move(SixDirection.Up, 1)
        builder.turn(TurnDirection.Left)
        builder.turn(TurnDirection.Left)
    }
    builder.tracePath(blocks.block(Block.MossyStoneBricks))
})
```