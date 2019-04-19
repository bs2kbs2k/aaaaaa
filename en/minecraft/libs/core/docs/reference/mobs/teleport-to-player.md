# teleport To Player

Teleport entities to a player.

```sig
mobs.teleportToPlayer(
    mobs.target(TargetSelectorKind.AllPlayers),
    mobs.target(TargetSelectorKind.LocalPlayer)
);
```

## Parameters

* **target**: a target selector that chooses which entities will be teleported
* **destination**: a target selector that determines which player the entities will be teleported to

## Example

Teleport all zombies to the current player. Run!

```blocks
mobs.teleportToPlayer(
    mobs.entitiesByType(mobs.monster(MonsterMob.Zombie)),
    mobs.target(TargetSelectorKind.LocalPlayer)
);
```

## See also

[`||mobs:teleport to position||`](/reference/mobs/teleport-to-position)