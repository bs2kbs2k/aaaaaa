# 원

중심점을 중심으로 원 모양을 만듭니다.

```sig
shapes.circle(blocks.block(Block.Grass), positions.create(0, 0, 0),
    0, Axis.X, ShapeOperation.Replace)
```

The circle has a ***radius*** which is the width from the center of the circle to its outside edge. The center of the circle is the middle point (position) that the circle surrounds.

You also decide what ***orientation*** that the circle has. This is will make the circle lay flat (using `y (up/down)`) or stand up vertically (using `x (East/West)` or `z (South/North)`). The orientation is the axis that the circle will wrap around.

## 매개 변수

* **block**: the type of block for the circle, such as: Block.HayBlock
* **center**: the position of the center of the circle
* **radius**: the radius of the circle, in blocks
* **orientation**: the axis that the circle will wrap around, like: Axis.Y
* **ShapeOperation**: the method for placing blocks, inside or around the circle

## 예시

Make a cool chat command. Form a circle of ice that the surrounds the current player to keep things cool.

```blocks
player.onChat("icering", function () {
    shapes.circle(
        blocks.block(Block.PackedIce),
        positions.create(0, 0, 0),
        5,
        Axis.Y,
        ShapeOperation.Outline
    )
})
```

## 참고 항목

[`||shapes:sphere||`](/reference/shapes/sphere)