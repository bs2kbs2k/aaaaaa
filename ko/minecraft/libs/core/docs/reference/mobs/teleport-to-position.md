# teleport To Position

Teleport entities to another location.

```sig
mobs.teleportToPosition(
    mobs.target(TargetSelectorKind.AllEntities),
    positions.create(0, 0, 0)
);
```

## 매개 변수

* **target**: a target selector that chooses which entities are teleported
* **destination**: the coordinates (position) where the selected entities are teleported to

## 예시

Teleport all chickens somewhere above the current player.

```blocks
mobs.teleportToPosition(
    mobs.entitiesByType(mobs.animal(AnimalMob.Chicken)),
    positions.create(0, 10, 0)
);
```

## 참고 항목

[`||mobs:teleport to player||`](/reference/mobs/teleport-to-player)