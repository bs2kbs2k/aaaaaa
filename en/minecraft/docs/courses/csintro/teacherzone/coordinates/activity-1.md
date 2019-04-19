# Activity: Create a Compass Rose

## Challenges

### Challenge 1 - Create a Bigger Compass

```blocks
player.onChat("compassrose", function () {
    blocks.fill(
    blocks.block(Block.GrayWool),
    positions.create(-20, -1, 0),
    positions.create(20, -1, 0),
    FillOperation.Replace
    )
    blocks.print(
    "W",
    blocks.block(Block.LimeWool),
    positions.create(-21, 0, 0),
    CompassDirection.West
    )
    blocks.print(
    "E",
    blocks.block(Block.YellowWool),
    positions.create(21, 0, 0),
    CompassDirection.West
    )
    blocks.fill(
    blocks.block(Block.GrayWool),
    positions.create(0, -1, -20),
    positions.create(0, -1, 20),
    FillOperation.Replace
    )
    blocks.print(
    "N",
    blocks.block(Block.BlueWool),
    positions.create(0, 0, -21),
    CompassDirection.West
    )
    blocks.print(
    "S",
    blocks.block(Block.RedWool),
    positions.create(0, 0, 21),
    CompassDirection.West
    )
})
```

### Challenge 2 - Build an Air Compass

```blocks
player.onChat("compassrose", function () {
    blocks.fill(
    blocks.block(Block.GrayWool),
    positions.create(-20, 50, 0),
    positions.create(20, 50, 0),
    FillOperation.Replace
    )
    blocks.print(
    "W",
    blocks.block(Block.LimeWool),
    positions.create(-21, 51, 0),
    CompassDirection.West
    )
    blocks.print(
    "E",
    blocks.block(Block.YellowWool),
    positions.create(21, 51, 0),
    CompassDirection.West
    )
    blocks.fill(
    blocks.block(Block.GrayWool),
    positions.create(0, 50, -20),
    positions.create(0, 50, 20),
    FillOperation.Replace
    )
    blocks.print(
    "N",
    blocks.block(Block.BlueWool),
    positions.create(0, 50, -21),
    CompassDirection.West
    )
    blocks.print(
    "S",
    blocks.block(Block.RedWool),
    positions.create(0, 50, 21),
    CompassDirection.West
    )
    blocks.fill(
    blocks.block(Block.GrayWool),
    positions.create(0, 70, 0),
    positions.create(0, 30, 0),
    FillOperation.Replace
    )
    blocks.print(
    "UP",
    blocks.block(Block.PurpleWool),
    positions.create(-2, 71, -1),
    CompassDirection.West
    )
    blocks.print(
    "DOWN",
    blocks.block(Block.OrangeWool),
    positions.create(-2, 29, -1),
    CompassDirection.West
    )
})
```

![compass rose in the sky](/static/courses/csintro/coordinates/compass-rose-sky.jpg)

**Shared Program:**

## Experiments

### Experiment 1 - Use Color for Directions

```blocks
player.onChat("compassrose", function () {
    blocks.fill(
    blocks.block(Block.RedStainedGlass),
    positions.create(-20, 50, 0),
    positions.create(20, 50, 0),
    FillOperation.Replace
    )
    blocks.print(
    "W",
    blocks.block(Block.LimeWool),
    positions.create(-21, 51, 0),
    CompassDirection.West
    )
    blocks.print(
    "E",
    blocks.block(Block.YellowWool),
    positions.create(21, 51, 0),
    CompassDirection.West
    )
    blocks.fill(
    blocks.block(Block.LimeStainedGlass),
    positions.create(0, 50, -20),
    positions.create(0, 50, 20),
    FillOperation.Replace
    )
    blocks.print(
    "N",
    blocks.block(Block.BlueWool),
    positions.create(0, 50, -21),
    CompassDirection.West
    )
    blocks.print(
    "S",
    blocks.block(Block.RedWool),
    positions.create(0, 50, 21),
    CompassDirection.West
    )
    blocks.fill(
    blocks.block(Block.BlueStainedGlass),
    positions.create(0, 70, 0),
    positions.create(0, 30, 0),
    FillOperation.Replace
    )
    blocks.print(
    "UP",
    blocks.block(Block.PurpleWool),
    positions.create(-2, 71, -1),
    CompassDirection.West
    )
    blocks.print(
    "DOWN",
    blocks.block(Block.OrangeWool),
    positions.create(-2, 29, -1),
    CompassDirection.West
    )
})
```

![compass rose painted axes](/static/courses/csintro/coordinates/compassrosepaintedaxes.jpg)

### Experiment 2 - Use Colors to Represent Other Compass Features

```blocks
player.onChat("compassrose", function () {
    blocks.fill(
    blocks.block(Block.RedStainedGlass),
    positions.create(-20, 50, 0),
    positions.create(20, 50, 0),
    FillOperation.Replace
    )
    blocks.print(
    "W",
    blocks.block(Block.RedGlazedTerracotta),
    positions.create(-21, 51, 0),
    CompassDirection.West
    )
    blocks.print(
    "E",
    blocks.block(Block.RedGlazedTerracotta),
    positions.create(21, 51, 0),
    CompassDirection.West
    )
    blocks.fill(
    blocks.block(Block.LimeStainedGlass),
    positions.create(0, 50, -20),
    positions.create(0, 50, 20),
    FillOperation.Replace
    )
    blocks.print(
    "N",
    blocks.block(Block.LimeGlazedTerracotta),
    positions.create(0, 50, -21),
    CompassDirection.West
    )
    blocks.print(
    "S",
    blocks.block(Block.GreenGlazedTerracotta),
    positions.create(0, 50, 21),
    CompassDirection.West
    )
    blocks.fill(
    blocks.block(Block.BlueStainedGlass),
    positions.create(0, 70, 0),
    positions.create(0, 30, 0),
    FillOperation.Replace
    )
    blocks.print(
    "UP",
    blocks.block(Block.BlueGlazedTerracotta),
    positions.create(-2, 71, -1),
    CompassDirection.West
    )
    blocks.print(
    "DOWN",
    blocks.block(Block.LightBlueGlazedTerracotta),
    positions.create(-2, 29, -1),
    CompassDirection.West
    )
})
```

![compass rose terracotta print](/static/courses/csintro/coordinates/compassroseprintdirections.jpg)

Other reference examples:

* [Compass Rose](/tutorials/compass-rose)
* [3D Axis](/examples/3d-axis)
* [Compass](/examples/compass)