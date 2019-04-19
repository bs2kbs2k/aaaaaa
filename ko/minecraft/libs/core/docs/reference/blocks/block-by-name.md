# block By Name

Represents a block or item from the game by its code name. All blocks and items in the game have a code name associated with them.

Read about block and item IDs here in the [Minecraft wiki](http://minecraft.gamepedia.com/Data_values#IDs).

```sig
blocks.blockByName("stone");
```

## 매개 변수

* **name** the name of the block, like: "stone"

## 예시

Give a torch to the local player. The code name for a torch is `torch`.

```blocks
mobs.give(
    mobs.target(TargetSelectorKind.LocalPlayer),
    blocks.blockByName("torch"),
    1
);
```

## 참고 항목

[`||blocks:item||`](/reference/blocks/item), [`||blocks:block||`](/reference/blocks/block)