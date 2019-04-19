# outside Radius

Sets the closest (minimum) distance from this selector's base coordinates. This is a useful way change the minimum distance of an existing target selector.

Only mobs that are farther than the distance chosen from this selector's coordinates are selected.

```sig
mobs.target(TargetSelectorKind.AllEntities).outsideRadius(0);
```

## 매개 변수

* **radius**: the minimum distance (in blocks) for this target selector, like: 10

## 예시

This code shows how to select all chickens between 10 and 20 blocks away from the player.

**First:** The code creates a target selector that selects all chickens within 20 blocks of the current player's world position. The target selector is stored in a variable called `item`.

**Then:** The selector's minimum radius is changed to `10`.

**Finally:** The selector is used in a teleport command. Because we changed the selector's minimum radius, chickens within 10 blocks of the player are not teleported.

```blocks
let item: TargetSelector = null;
item = mobs.near(
    mobs.entitiesByType(mobs.animal(AnimalMob.Chicken)),
    player.position(),
    20
);
item.outsideRadius(10);
mobs.teleportToPosition(
    item,
    positions.create(0, 10, 0)
);
```

## 참고 항목

[`||mobs:within radius||`](/reference/mobs/selectors/within-radius)

You can read about how target selectors work in the [Minecraft wiki](http://minecraft.gamepedia.com/Commands#Target_selectors).