# block By Id

Represents a block or item from the game by its value identifier (ID). All blocks and items in the game have an ID associated with them.

Read about block and item IDs here in the [Minecraft wiki](http://minecraft.gamepedia.com/Data_values#IDs).

```sig
blocks.blockById(0);
```

## Parameters

* **id** the ID of the block or item from the game

## Example

Give a leather helmet to the player. The ID of the leather helmet item is 298.

```blocks
mobs.give(
    mobs.target(TargetSelectorKind.LocalPlayer),
    blocks.blockById(298),
    1
);
```

## See Also

[`||blocks:item||`](/reference/blocks/item), [`||blocks:block||`](/reference/blocks/block)