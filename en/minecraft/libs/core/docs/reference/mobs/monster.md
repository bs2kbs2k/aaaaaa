# monster

A monster mob in the game.

```sig
mobs.monster(MonsterMob.Creeper);
```

## Parameters

* **name**: the type of the monster

## Example

Spawn a spider near the player.

```blocks
mobs.spawn(mobs.monster(MonsterMob.Spider), positions.create(5, 0, 0))
```

## See also

[`||mobs:spawn||`](/reference/mobs/spawn)