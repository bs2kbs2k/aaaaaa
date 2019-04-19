# sphere

Fill a sphere of blocks at a center position.

```sig
shapes.sphere(
    blocks.block(Block.Grass),
    positions.create(0, 0, 0),
    0,
    ShapeOperation.Replace
)
```

The sphere has a ***radius*** which is the distance from the center of the sphere to its outside edge. The center of the sphere is the middle point (position) that the sphere surrounds.

## Parameters

* **block**: the type of block for the sphere, such as: Block.Gravel
* **center**: the position of the center of the sphere
* **radius**: the radius of the sphere, in blocks
* **ShapeOperation**: the method for placing blocks, inside or around the sphere

## Example

Make a chat command to suspend a ball of granite above the player. Let's hope it doesn't fall!

```blocks
player.onChat("toprock", function () {
    shapes.sphere(
        blocks.block(Block.Granite),
        positions.create(0, 5, 0),
        3,
        ShapeOperation.Replace
    )
})
```

## See also

[`||shapes:circle||`](/reference/shapes/circle)