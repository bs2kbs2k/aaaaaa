# Cubic units

Students create shapes using code and then determine the number of cubic units that combined shapes would make.

## Learning objectives

Play with the parameters such as height, width, and amount of lava to predict and test the effects of different sized volcanoes on the earth around it.

## ~ hint

#### Applicability

**Skill areas**: Math, Volume, Cubic Units

**Ages**: 11-12 yrs old

**Grade level**: 5th

## ~

## Guiding ideas

Recognize volume as an attribute of solid figures and understand concepts of volume measurement. Measure volumes by counting unit cubes, using cubic units of *cm*, *in*, *ft*, and improvised units. Relate volume to the operations of multiplication and addition by solving conceptual and real world problems involving volume.

#### Related Common Core math standards:

* [CCSS.MATH.CONTENT.5.MD.C.3](http://www.corestandards.org/Math/Content/5/MD/C/3)
* [CCSS.MATH.CONTENT.5.MD.C.4](http://www.corestandards.org/Math/Content/5/MD/C/4)
* [CCSS.MATH.CONTENT.5.MD.C.5](http://www.corestandards.org/Math/Content/5/MD/C/5)

## 학생 학습 활동

This activity requires students to have the *Code Connection* app open and running with their *Minecraft Education Edition*.

이 활동은 2개의 부분으로 이루어져 있습니다.:

* [Creating 3D quadrilaterals](#creating-3d-quadrilaterals)
* [Determine the Volume of combined quadrilaterals](#determine-the-volume-of-combined-quadrilaterals)

### Creating 3D quadrilaterals

Using code, have students create quadrilaterals in Minecraft. For example, a cube with a volume of 1000 cubic units would be:

```blocks
player.onChat("cube", function () {
    blocks.fill(
    blocks.block(Block.EmeraldBlock),
    positions.create(0, 0, 0),
    positions.create(10, 10, 10),
    FillOperation.Replace
    )
})
```

Have students create quadrilaterals of different sizes and write down the volume for each one using the [Cubic Units Worksheet](/lessons/cubic/worksheet).

### Determine the volume of combined quadrilaterals

Using the four quadrilaterals that your students have already made, have them combine them into one large quadrilateral. For example, if these are the four quadrilaterals:

```blocks
player.onChat("shape1", function () {
    blocks.fill(
    blocks.block(Block.EmeraldBlock),
    positions.create(0, 0, 0),
    positions.create(10, 10, 10),
    FillOperation.Replace
    )
})
player.onChat("shape2", function () {
    blocks.fill(
        blocks.block(Block.Bricks),
        positions.create(0, 0, 0),
        positions.create(5, 10, 5),
        FillOperation.Replace
    )
})
player.onChat("shape3", function () {
    blocks.fill(
        blocks.block(Block.PlanksSpruce),
        positions.create(0, 0, 0),
        positions.create(5, 7, 5),
        FillOperation.Replace
    )
})
player.onChat("shape4", function () {
    blocks.fill(
        blocks.block(Block.Wool),
        positions.create(0, 0, 0),
        positions.create(5, 3, 5),
        FillOperation.Replace
    )
})
```

Have students add offsets to the code for each shape command to make one large quadrilateral:

```blocks
player.onChat("shape1", function () {
    blocks.fill(
    blocks.block(Block.EmeraldBlock),
    positions.create(0, 0, 0),
    positions.create(10, 10, 10),
    FillOperation.Replace
    )
})
player.onChat("shape2", function () {
    blocks.fill(
        blocks.block(Block.Bricks),
        positions.create(10, 0, 0),
        positions.create(5, 10, 5),
        FillOperation.Replace
    )
})
player.onChat("shape3", function () {
    blocks.fill(
        blocks.block(Block.PlanksSpruce),
        positions.create(10, 0, 5),
        positions.create(5, 7, 5),
        FillOperation.Replace
    )
})
player.onChat("shape4", function () {
    blocks.fill(
        blocks.block(Block.Wool),
        positions.create(10, 7, 5),
        positions.create(5, 3, 5),
        FillOperation.Replace
    )
})
player.onChat("large", function () {
    player.runChatCommand("shape1")
    player.runChatCommand("shape2")
    player.runChatCommand("shape3")
    player.runChatCommand("shape4")
})
```

Calculate the volume of the large quadrilateral based on the volume of the smaller quadrilaterals. Then, confirm that volume by counting the number of blocks created with your program.

Lead a discussion on how the volume would change (or not) if the combined four shapes did not create a perfect quadrilateral (e.g. they were a pyramid instead).

## Performance Expectations

#### Intended outcomes:

* Understanding how volume is calculated with length, width, and height.
* Visualizing volume with 3D Minecraft blocks.
* Understanding how to combine quadrilaterals to create new quadrilaterals.
* Understanding how to calculate volume of large shapes based on smaller shapes.

## 자료

[Cubic Units Worksheet](/lessons/cubic/worksheet)