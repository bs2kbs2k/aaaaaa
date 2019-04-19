# item

Represents an item from the game.

```sig
blocks.item(Item.IronShovel);
```

## Parameters

* **item**: the item

## Example

Give a diamond to the current player.

```blocks
mobs.give(
    mobs.target(TargetSelectorKind.LocalPlayer),
    blocks.item(Item.Diamond),
    1
);
```

## See Also

[`||blocks:block||`](/reference/blocks/block)