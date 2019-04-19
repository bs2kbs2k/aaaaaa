# entities By Type

Selects all mobs (animals or monsters) of the type you want to target.

```sig
mobs.entitiesByType(mobs.animal(AnimalMob.Chicken));
```

## Parameters

* **type**: the type of mob to select

## Example

Teleport all chickens high in the sky.

```blocks
mobs.teleportToPosition(
    mobs.entitiesByType(mobs.animal(AnimalMob.Chicken)),
    positions.create(0, 30, 0)
);
```

## See also

[`||mobs:target||`](reference/mobs/target)