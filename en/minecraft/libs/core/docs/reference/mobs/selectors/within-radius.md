# within Radius

Sets the farthest (maximum) distance from this selector's base coordinates. This is a useful way to change the maximum distance of an existing target selector.

Only mobs that are within this distance from the selector's coordinates are selected.

```sig
mobs.target(TargetSelectorKind.AllEntities).withinRadius(0);
```

## Parameters

* **radius**: the maximum distance (in blocks) for this target selector, like: 5

## Example

**First:** This code creates a target selector to select all chickens within 5 blocks of the current player's world position. The target selector is stored in a variable called `item`.

**Then:** The target selector is changed to select chickens within 30 blocks of the player, instead of 5.

**Finally:** The selector is used in a teleport command. Because we changed the selector's radius, all chickens now within 30 blocks (not 5 blocks like before) of the current player are teleported.

```blocks
let item: TargetSelector = null;
item = mobs.near(
    mobs.entitiesByType(mobs.animal(AnimalMob.Chicken)),
    player.position(),
    5
);
item.withinRadius(30);
mobs.teleportToPosition(
    item,
    positions.create(0, 10, 0)
);
```

## See also

[`||mobs:outside radius||`](/reference/mobs/selectors/outside-radius)

You can read about how target selectors work in the [Minecraft wiki](http://minecraft.gamepedia.com/Commands#Target_selectors).