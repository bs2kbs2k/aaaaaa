# circle

Fill a circle of blocks at a center position.

```sig
shapes.circle(blocks.block(Block.Grass), positions.create(0, 0, 0),
    0, Axis.X, ShapeOperation.Replace)
```

The circle has a ***radius*** which is the width from the center of the circle to its outside edge. The center of the circle is the middle point (position) that the circle surrounds.

You also decide what ***orientation*** that the circle has. This is will make the circle lay flat (using `y (up/down)`) or stand up vertically (using `x (East/West)` or `z (South/North)`). The orientation is the axis that the circle will wrap around.

## Parameters

* **block**: the type of block for the circle, such as: Block.HayBlock
* **center**: the position of the center of the circle
* **radius**: the radius of the circle, in blocks
* **orientation**: the axis that the circle will wrap around, like: Axis.Y
* **ShapeOperation**: the method for placing blocks, inside or around the circle

## Example

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

## See also

[`||shapes:sphere||`](/reference/shapes/sphere)