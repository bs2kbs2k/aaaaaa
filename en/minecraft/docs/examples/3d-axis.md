# A giant 3D axis

![A 3D axis symbol](/static/mods/3d-axis.jpg)

Where is the world heading? You can know where with all three axes printed to see. This is a great way to learn how [positions](/reference/positions) work.

## Try the code:

```blocks
let pz: Position = null
let py: Position = null
let px: Position = null
let p: Position = null
player.onChat("axis", function () {
    p = player.position()

    px = positions.add(p, positions.create(20, 0, 0))
    blocks.fill(
        blocks.block(Block.Obsidian),
        p,
        px,
        FillOperation.Replace
    )
    blocks.print(
        "X",
        blocks.block(Block.RedstoneBlock),
        px,
        CompassDirection.East
    )
    py = positions.add(p, positions.create(0, 20, 0))
    blocks.fill(
        blocks.block(Block.Obsidian),
        p,
        py,
        FillOperation.Replace
    )
    blocks.print(
        "Y",
        blocks.block(Block.RedstoneBlock),
        py,
        CompassDirection.East
    )
    pz = positions.add(p, positions.create(0, 0, 20))
    blocks.fill(
        blocks.block(Block.Obsidian),
        p,
        pz,
        FillOperation.Replace
    )
    blocks.print(
        "Z",
        blocks.block(Block.RedstoneBlock),
        pz,
        CompassDirection.East
    )

    blocks.print(
        p.getValue(Axis.X) + "," + p.getValue(Axis.Y) + "," + p.getValue(Axis.Z),
        blocks.block(Block.RedstoneBlock),
        positions.add(p, positions.create(-30, 0, 0)),
        CompassDirection.North
    )
})
```