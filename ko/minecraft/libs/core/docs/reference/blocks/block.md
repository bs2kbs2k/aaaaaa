# 블록

A block item from the game.

```sig
blocks.block(Block.Grass);
```

## 매개 변수

* **block**: the block

## 예시

Place a block of diamond near the player.

```blocks
blocks.place(blocks.block(Block.DiamondBlock), positions.create(1, 0, 0));
```

## 참고 항목

[`||blocks:item||`](/reference/blocks/item)