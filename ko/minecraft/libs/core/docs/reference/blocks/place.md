# place

Place a block in the world at a position you choose.

```sig
blocks.place(blocks.block(Block.Grass), positions.create(0, 0, 0));
```

## 매개 변수

* **block**: the block to place
* **pos**: the position at which to place the block

## 예시

Continuously place a block of gold underneath your feet.

```blocks
loops.forever(() => {
    blocks.place(blocks.block(Block.GoldBlock), positions.create(0, -1, 0));
});
```