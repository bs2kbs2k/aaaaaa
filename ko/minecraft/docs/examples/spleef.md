# 스플리프

![Spleef game board](/static/mods/spleef.jpg)

The popular **spleef** mini-game.

## Try the code:

```blocks
player.onChat("spleef", function (num1) {
    blocks.fill(
        blocks.block(Block.Lava),
        positions.create(0, -1, 0),
        positions.create(num1, -1, num1),
        FillOperation.Replace
    )
    blocks.fill(
        blocks.block(Block.Snow),
        positions.create(0, 4, 0),
        positions.create(num1, 4, num1),
        FillOperation.Replace
    )
    mobs.teleportToPosition(
        mobs.target(TargetSelectorKind.AllPlayers),
        positions.create(num1 / 2, 5, num1 / 2)
    )
    gameplay.setGameMode(
        GameMode.Survival,
        mobs.target(TargetSelectorKind.AllPlayers)
    )
})
```