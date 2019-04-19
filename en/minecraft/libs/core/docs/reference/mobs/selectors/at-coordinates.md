# at Coordinates

Give new coordinates, a position, to a target selector. This is useful way to change the position of an existing target.

```sig
mobs.target(TargetSelectorKind.AllEntities).atCoordinate(positions.create(0, 0, 0));
```

## Parameters

* **p**: set the selector to these coordinates

## Example

First, this code creates a target selector to select all chickens within `30` blocks in any direction of the world position `5` `0` `5`. The target selector is stored in a variable called `flyingChickens`.

Then, the target selector is changed so its position is centered on the current player's position instead of the original position of `5` `0` `5`. So, when it is used, the target selector will now select chickens `30` blocks from the current player's position.

Finally, the selector with the new position is used in a teleport command. The chickens found near the new location by the current player are teleported.

```blocks
let flyingChickens: TargetSelector = null;
flyingChickens = mobs.near(
    mobs.entitiesByType(mobs.animal(AnimalMob.Chicken)),
    positions.createWorld(5, 0, 5),
    30
);
flyingChickens.atCoordinate(player.position());
mobs.teleportToPosition(
    flyingChickens,
    positions.create(0, 10, 0)
);
```