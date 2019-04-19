# 신뢰의 도약

![Standing on the edge of a platform](/static/mods/leap-of-faith.jpg)

Jump from the platform into the pool!

## Try the code:

```blocks
player.onChat("lof", function () {
    blocks.fill(
        blocks.block(Block.Water),
        positions.create(-1, -3, -1),
        positions.create(1, -1, 1)
    )
    blocks.fill(
        blocks.block(Block.Stone),
        positions.create(-1, 128, -1),
        positions.create(1, 128, 1)
    )
    player.teleport(positions.create(0, 130, 0))
    gameplay.setGameMode(
        GameMode.Survival,
        mobs.target(TargetSelectorKind.NearestPlayer)
    )
})
```