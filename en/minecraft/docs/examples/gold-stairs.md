# Gold Stairs

![Gold stairs going up](/static/mods/gold-stairs.jpg)

Climb to a whole new level and do it in style!

## Try the code:

```blocks
player.onChat("goldstairs", function () {
    builder.teleportTo(positions.create(0, 0, 0))
    for (let i = 0; i < 25; i++) {
        builder.move(SixDirection.Forward, 1)
        builder.move(SixDirection.Up, 1)
    }
    builder.tracePath(blocks.block(Block.GoldBlock))
    mobs.teleportToPosition(
        mobs.target(TargetSelectorKind.AllPlayers),
        positions.create(0, 0, 0)
    )
    gameplay.setGameMode(
        GameMode.Survival,
        mobs.target(TargetSelectorKind.AllPlayers)
    )    
})

```

```package
builder
```