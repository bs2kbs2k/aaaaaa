# color To Block

Represents a colored block from the game. Wool and concrete can have multiple colors.

```sig
blocks.colorToBlock(ColoredBlock.Wool, blocks.color(BlockColor.White));
```

## 매개 변수

* **type** the type of block, either `wool` or `concrete`
* **color** the color of the block

## 예시

Place orange concrete near the player.

```blocks
blocks.place(blocks.colorToBlock(ColoredBlock.Concrete, blocks.color(BlockColor.Orange)), positions.create(1, 0, 0));
```

## 참고 항목

[`||blocks:color||`](/reference/blocks/color)