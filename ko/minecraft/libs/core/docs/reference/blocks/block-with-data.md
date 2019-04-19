# block With Data

Represents a block or item from the game with a data value. Some blocks and items have a certain *state* associated with them. The *state* is a `number` kept with the block or item.

More information about data values is in the [Minecraft wiki](http://minecraft.gamepedia.com/Data_values#Data).

```sig
blocks.blockWithData(blocks.block(Block.Grass), 0);
```

## 매개 변수

* **b** the block or item
* **data** the data value for the block or item

## 예시

Wood planks are a special type of block that use data values to determine the wood texture. The data value for the acacia wood type is `4`. This code places a block of acacia planks near the player.

```blocks
blocks.place(blocks.blockWithData(blocks.block(Block.PlanksOak), 4), positions.create(1, 0, 0))
```

There are items that also use data values. The bed item uses data values for the color of the bed. This code gives a blue bed to the player (the data value for the blue-colored bed is 11).

```blocks
mobs.give(
    mobs.target(TargetSelectorKind.LocalPlayer),
    blocks.blockWithData(blocks.item(Item.Bed), 11),
    1
);
```

## 참고 항목

[`||blocks:item||`](/reference/blocks/item), [`||blocks:block||`](/reference/blocks/block)