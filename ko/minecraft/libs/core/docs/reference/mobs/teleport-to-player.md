# teleport To Player

Teleport entities to a player.

```sig
mobs.teleportToPlayer(
    mobs.target(TargetSelectorKind.AllPlayers),
    mobs.target(TargetSelectorKind.LocalPlayer)
);
```

## 매개 변수

* **target**: a target selector that chooses which entities will be teleported
* **destination**: a target selector that determines which player the entities will be teleported to

## 예시

Teleport all zombies to the current player. Run!

```blocks
mobs.teleportToPlayer(
    mobs.entitiesByType(mobs.monster(MonsterMob.Zombie)),
    mobs.target(TargetSelectorKind.LocalPlayer)
);
```

## 참고 항목

[`||mobs:teleport to position||`](/reference/mobs/teleport-to-position)