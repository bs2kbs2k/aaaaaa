# near

Selects targets near a position.

```sig
mobs.near(
    mobs.target(TargetSelectorKind.LocalPlayer),
    positions.createWorld(0, 0, 0),
    5
);
```

## 매개 변수

* **target**: the type of mobs to select: > * `local player`: select the current player (you) > * `nearest player`: select the player nearest to the world origin > * `random player`: select a random player in the world > * `all players`: select all players in the world > * `all entities`: select all players and mobs
* **pos**: the position near where you want to select targets
* **radius**: how far away (in blocks) you want to go to select targets, like: `5` blocks

## 예시

Teleport all chickens within 15 blocks of the player high in the sky.

```blocks
mobs.teleportToPosition(
    mobs.near(
        mobs.entitiesByType(mobs.animal(AnimalMob.Chicken)),
        player.position(),
        15
    ),
    positions.create(0, 30, 0)
);
```

## 참고 항목

[`||mobs:target||`](/reference/selectors/target), [`||positions:positions||`](/reference/positions)

Read more about target selectors in the [Minecraft wiki](http://minecraft.gamepedia.com/Commands#Target_selectors).