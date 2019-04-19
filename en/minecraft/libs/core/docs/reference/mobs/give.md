# give

Give blocks or items from the game to other players.

```sig
mobs.give(mobs.target(TargetSelectorKind.NearestPlayer), blocks.block(Block.TNT), 1);
```

## Parameters

* **target**: a target selector that determines which players will receive the block or item
* **block**: the block or item you want to give
* **amount**: how many to give, like: 1

## Example

Give 10 TNT blocks to all players.

```blocks
mobs.give(mobs.target(TargetSelectorKind.AllPlayers), blocks.block(Block.TNT), 10);
```