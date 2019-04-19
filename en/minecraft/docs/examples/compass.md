# Compass

![Compass symbol](/static/mods/compass.jpg)

A giant compass with heading labels. Another use of block printing and [positions](/reference/positions).

## Try the code:

```blocks
let north: Position = null
let south: Position = null
let west: Position = null
let east: Position = null
let up: Position = null
let down: Position = null
let p: Position = null
let length = 25
player.onChat("compass", function () {
    p = player.position()

    east = positions.add(p, positions.create(length, 0, 0))
    blocks.fill(
        blocks.block(Block.Obsidian),
        p,
        east,
        FillOperation.Replace
    )
    blocks.print(
        "EAST+X",
        blocks.block(Block.RedstoneBlock),
        east,
        CompassDirection.East
    )

    west = positions.add(p, positions.create(-length, 0, 0))
    blocks.fill(
        blocks.block(Block.Obsidian),
        p,
        west,
        FillOperation.Replace
    )
    blocks.print(
        "WEST-X",
        blocks.block(Block.RedstoneBlock),
        positions.add(west, positions.create(-30, 0, 0)),
        CompassDirection.East
    )

    up = positions.add(p, positions.create(0, length, 0))
    blocks.fill(
        blocks.block(Block.Obsidian),
        p,
        up,
        FillOperation.Replace
    )
    blocks.print(
        "UP+Y",
        blocks.block(Block.RedstoneBlock),
        up,
        CompassDirection.East
    )

    down = positions.add(p, positions.create(0, -length, 0))
    blocks.fill(
        blocks.block(Block.Obsidian),
        p,
        down,
        FillOperation.Replace
    )
    blocks.print(
        "DOWN-Y",
        blocks.block(Block.RedstoneBlock),
        down,
        CompassDirection.East
    )

    north = positions.add(p, positions.create(0, 0, -length))
    blocks.fill(
        blocks.block(Block.Obsidian),
        p,
        north,
        FillOperation.Replace
    )
    blocks.print(
        "NORTH-Z",
        blocks.block(Block.RedstoneBlock),
        north,
        CompassDirection.East
    )

    south = positions.add(p, positions.create(0, 0, length))
    blocks.fill(
        blocks.block(Block.Obsidian),
        p,
        south,
        FillOperation.Replace
    )
    blocks.print(
        "SOUTH+Z",
        blocks.block(Block.RedstoneBlock),
        south,
        CompassDirection.East
    )
})
```