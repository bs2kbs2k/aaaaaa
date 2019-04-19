# GAME OVER!

![Game over message](/static/mods/game-over.jpg)

Change the rules and players can't come back. Drop them into the abyss and before they know it, you changed their game mode too.

### ~ hint

**GRIEFING ALERT**

This mod will suddenly teleport all players into the void.

### ~

## Try the code:

```blocks
player.onChat("gameover", function () {
    gameplay.setGameMode(
        GameMode.Survival,
        mobs.target(TargetSelectorKind.AllPlayers)
    )
    mobs.teleportToPosition(mobs.target(TargetSelectorKind.AllPlayers), positions.create(0, -1000, 0))
    loops.pause(1000)
    gameplay.setGameMode(
        GameMode.Creative,
        mobs.target(TargetSelectorKind.AllPlayers)
    )
})
```