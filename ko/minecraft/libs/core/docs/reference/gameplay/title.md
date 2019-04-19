# title

Displays a title, subtitle to the selected players.

```sig
gameplay.title(mobs.target(TargetSelectorKind.AllPlayers), "Title", "Sub title");
```

This block is very useful to give instructions on mini games.

## 매개 변수

* **target**: a target selector that determines which players will receive the block or item
* **title**: the large font title to display
* **sub title**: the secondary title to display (optional)

## 예시

In the treasure mini-game below, a diamond is placed randomly around the current positions. All players are then teleported to the location and shown a message to start looking for the diamond.

```blocks
player.onChat("hunt", function () {
    blocks.place(blocks.block(Block.DiamondBlock), positions.create(Math.randomRange(-10, 10), Math.randomRange(-3, -2), Math.randomRange(-10, 10)))
    mobs.teleportToPosition(
    mobs.target(TargetSelectorKind.AllPlayers),
    positions.create(0, 0, 0)
    )
    gameplay.title(mobs.target(TargetSelectorKind.AllPlayers), "READY?", "Find the hidden diamond!")
})
```