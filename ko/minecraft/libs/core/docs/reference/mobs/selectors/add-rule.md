# add Rule

Add a rule (called *arguments* in the Minecraft wiki) to this target selector. Rules are a useful way to change the behavior of an existing target selector.

```sig
mobs.target(TargetSelectorKind.AllEntities).addRule("type", "chicken");
```

## 매개 변수

* **rule**: the rule you want to add, such as: "type"
* **value**: the value for the rule, like: "chicken"

The [Minecraft wiki](http://minecraft.gamepedia.com/Commands#Target_selector_arguments) has a list of available rule (argument) types and values. Not all the rules listed in the wiki will work in Minecraft Education Edition.

## 예시

**First:** This code creates a target selector that selects all entities. The target selector is stored in a variable called `item`.

**Then:** A rule is added to the target selector to select only cows.

**Finally:** The selector is used in a teleport command. Because we added a `type` rule, only cows will be teleported, even if the selector was set in **First** to select all entities in the world.

```blocks
let item: TargetSelector = null;
item = mobs.target(TargetSelectorKind.AllEntities);
item.addRule("type", "cow");
mobs.teleportToPosition(
    item,
    positions.create(0, 0, 0)
);
```

## 참고 항목

You can read about how target selectors work in the [Minecraft wiki](http://minecraft.gamepedia.com/Commands#Target_selectors).