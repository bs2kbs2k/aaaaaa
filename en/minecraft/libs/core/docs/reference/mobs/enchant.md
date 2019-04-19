# enchant

Add an enchantment to a target or to some targets (players).

The enchantment is added to the tool that the target player has now. If the target's current tool (or other item they have) is not enchantable, then the enchantment won't work and it isn't added.

```sig
mobs.enchant(mobs.target(TargetSelectorKind.LocalPlayer), "infinity", 1);
```

## Parameters

* **target**: a target selector that determines which players (targets) will get the enchantment
* **spell**: the code name of the enchantment, like: "infinity"
* **level**: the strength level of the enchantment, such as: 1

A summary of enchantments, including their effect and their maximum level, is in the [Minecraft wiki](http://minecraft.gamepedia.com/Enchanting#Summary_of_enchantments).

The names of the enchantments are in the [this section of the Minecraft wiki](http://minecraft.gamepedia.com/Enchanting#Data_values). Look in the column labeled "name".

## Example

Enchant the tool that current player has so it lasts longer.

```blocks
mobs.enchant(mobs.target(TargetSelectorKind.LocalPlayer), "unbreaking", 3);
```