# entities By Type

Selects all mobs (animals or monsters) of the type you want to target.

```sig
mobs.entitiesByType(mobs.animal(AnimalMob.Chicken));
```

## 매개 변수

* **type**: the type of mob to select

## 예시

Teleport all chickens high in the sky.

```blocks
mobs.teleportToPosition(
    mobs.entitiesByType(mobs.animal(AnimalMob.Chicken)),
    positions.create(0, 30, 0)
);
```

## 참고 항목

[`||mobs:target||`](reference/mobs/target)