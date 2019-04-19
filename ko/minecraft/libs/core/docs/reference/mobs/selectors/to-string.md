# to String

Return a string that has the game name (notation) for this target selector.

```sig
mobs.target(TargetSelectorKind.AllEntities).toString();
```

When used inside a `||player:say||` block, this block will print the names of selected entities. This can be useful to see a list of every entity in your world!

## 예시

This code prints a list of all entities in the current world.

```blocks
let mySelector: TargetSelector = null
mySelector = mobs.target(TargetSelectorKind.AllEntities)
player.say(mySelector.toString())
```

## 참고 항목

You can read about how target selectors work in the [Minecraft wiki](http://minecraft.gamepedia.com/Commands#Target_selectors).