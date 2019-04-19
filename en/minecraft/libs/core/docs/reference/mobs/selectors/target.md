# target

Chooses a group of players or mobs.

```sig
mobs.target(TargetSelectorKind.LocalPlayer);
```

## Parameters

* **kind**: the type of mobs to select: > * `local player`: select the current player (you) > * `nearest player`: select the player nearest to the world origin > * `random player`: select a random player in the world > * `all players`: select all players in the world > * `all entities`: select all players and mobs

## Example

Teleport all players, animals and monsters to the current player.

```blocks
mobs.teleportToPlayer(
    mobs.target(TargetSelectorKind.AllEntities),
    mobs.target(TargetSelectorKind.LocalPlayer)
);
```

## See Also

Using target selectors is described in the [Minecraft wiki](http://minecraft.gamepedia.com/Commands#Target_selectors).