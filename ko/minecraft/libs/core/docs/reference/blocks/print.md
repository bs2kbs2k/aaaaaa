# print

Create some text in the game world. The text is made of a type of block you choose at the position you want.

```sig
blocks.print(
    "HELLO",
    blocks.block(Block.Grass),
    positions.create(0, 0, 0),
    CompassDirection.West
);
```

## 매개 변수

* **text**: the text to print in the world, like: "HELLO"
* **block**: the block type that is used to create the text
* **position**: position, or coordinates, where the text is printed in the world
* **direction**: direction, the axis, along which the text is printed

## 예시

The following code writes "Hi!" in the sky near the player using gold blocks.

```blocks
blocks.print(
    "Hi!",
    blocks.block(Block.GoldBlock),
    positions.create(5, 2, 5),
    CompassDirection.West
);
```