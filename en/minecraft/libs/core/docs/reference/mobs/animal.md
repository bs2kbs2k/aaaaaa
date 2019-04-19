# animal

An animal mob in the game.

```sig
mobs.animal(AnimalMob.Pig);
```

## Parameters

* **name**: the type of animal

## Example

Spawn a sheep near the player.

```blocks
mobs.spawn(mobs.animal(AnimalMob.Sheep), positions.create(1, 0, 0));
```

## See also

[`||mobs:spawn||`](/reference/mobs/spawn)