# block By Id

Represents a block or item from the game by its value identifier (ID). All blocks and items in the game have an ID associated with them.

Read about block and item IDs here in the [Minecraft wiki](http://minecraft.gamepedia.com/Data_values#IDs).

```sig
blocks.blockById(0);
```

## 매개 변수

* **id** the ID of the block or item from the game

## 예시

Give a leather helmet to the player. The ID of the leather helmet item is 298.

```blocks
mobs.give(
    mobs.target(TargetSelectorKind.LocalPlayer),
    blocks.blockById(298),
    1
);
```

## 참고 항목

[`||blocks:item||`](/reference/blocks/item), [`||blocks:block||`](/reference/blocks/block)