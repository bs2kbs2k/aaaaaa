# Bomber Man

```blocks
player.onChat("bomberman", function () {
    blocks.fill(
        Block.Bedrock,
        positions.create(0, 50, 0),
        positions.create(20, 50, 20),
        FillOperation.Replace
    )
    blocks.fill(
        76,
        positions.create(0, 51, 0),
        positions.create(20, 51, 20),
        FillOperation.Replace
    )
    blocks.fill(
        blocks.block(Block.Dirt),
        positions.create(0, 52, 0),
        positions.create(20, 52, 20),
        FillOperation.Replace
    )
    mobs.teleportToPosition(
        mobs.target(TargetSelectorKind.AllPlayers),
        positions.create(10 / 2, 55, 10 / 2)
    )
    mobs.give(mobs.target(TargetSelectorKind.AllPlayers), Block.TNT, 64)
    gameplay.setGameMode(
        GameMode.Survival,
        mobs.target(TargetSelectorKind.AllPlayers)
    )
})
```