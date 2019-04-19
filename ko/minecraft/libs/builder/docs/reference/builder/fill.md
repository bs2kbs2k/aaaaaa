# fill

Fill a space shaped like a cube. The space is formed from the current position to the previous mark.

```sig
builder.fill(blocks.block(Block.Grass));
```

## 매개 변수

* **block**: the type of block used to fill the region

## 예시

Use the builder's fill operation to create a large cube of TNT near the player.

```blocks
builder.teleportTo(positions.create(0, 2, 0));
builder.shift(5, 5, 5);
builder.fill(blocks.block(Block.TNT));
```

## 참고 항목

Here's an example project that uses the builder: [Build a house](/examples/house-builder).