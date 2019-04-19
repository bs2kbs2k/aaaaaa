# place

Place a block at the current location and set the mark.

```sig
builder.place(blocks.block(Block.Grass));
```

The `||builder:place||` code block is used to place individual blocks. The builder's mark resets to the builder's current location when a block is placed.

## 매개 변수

* **block**: the type of block to place, like: Block.DiamondBlock

## 예시

Use the builder to place a block of diamond above the player.

```blocks
builder.teleportTo(positions.create(0, 2, 0));
builder.place(blocks.block(Block.DiamondBlock));
```

## 참고 항목

[`||builder:mark||`](/reference/builder/mark)

Here's an example project that uses the builder: [Build a house](/examples/house-builder).