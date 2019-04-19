# on Block Broken

Run code when a certain type of block is mined or broken.

```sig
blocks.onBlockBroken(blocks.block(Block.Grass), () => {

});
```

## 매개 변수

* **block**: the type of block that, when it is broken, will start some code
* **handler**: this is the code to run when the type of block selected in **block** is mined or broken

## 예시

When diamond ore is mined this code makes a new block of diamond near the current player. Unlimited diamonds!

```blocks
blocks.onBlockBroken(blocks.block(Block.DiamondOre), () => {
    blocks.place(blocks.block(Block.DiamondOre), positions.create(1, 0, 0));
});
```

## 참고 항목

[`||blocks:on block placed||`](/reference/blocks/on-block-placed)