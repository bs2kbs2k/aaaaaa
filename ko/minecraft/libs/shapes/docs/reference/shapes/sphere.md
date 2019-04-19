# 공모양

중심점을 중심으로 공 모양을 만듭니다.

```sig
shapes.sphere(
    blocks.block(Block.Grass),
    positions.create(0, 0, 0),
    0,
    ShapeOperation.Replace
)
```

The sphere has a ***radius*** which is the distance from the center of the sphere to its outside edge. The center of the sphere is the middle point (position) that the sphere surrounds.

## 매개 변수

* **block**: the type of block for the sphere, such as: Block.Gravel
* **center**: the position of the center of the sphere
* **radius**: the radius of the sphere, in blocks
* **ShapeOperation**: the method for placing blocks, inside or around the sphere

## 예시

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

## 참고 항목

[`||shapes:circle||`](/reference/shapes/circle)