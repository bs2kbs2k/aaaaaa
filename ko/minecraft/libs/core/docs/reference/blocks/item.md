# item

Represents an item from the game.

```sig
blocks.item(Item.IronShovel);
```

## 매개 변수

* **item**: the item

## 예시

Give a diamond to the current player.

```blocks
mobs.give(
    mobs.target(TargetSelectorKind.LocalPlayer),
    blocks.item(Item.Diamond),
    1
);
```

## 참고 항목

[`||blocks:block||`](/reference/blocks/block)