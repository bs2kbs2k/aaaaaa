# projectile

A projectile in the game.

```sig
mobs.projectile(ProjectileMob.LightningBolt);
```

## Parameters

* **name**: the type of the projectile

## Example

Trigger lightning near the player.

```blocks
mobs.spawn(mobs.projectile(ProjectileMob.LightningBolt), positions.create(5, 0, 0))
```

## See also

[`||mobs:spawn||`](/reference/mobs/spawn)