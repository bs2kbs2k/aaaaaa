# Cannon builder

![Two rows of TNT set to explode](/static/mods/cannon.jpg)

This awesome tutorial video shows how to build a TNT cannon in Minecraft. Let's automate it with the builder!

https://youtu.be/bgyC0Axje9Y

## Try the code:

```blocks
player.onChat("cannon", function () {
    builder.teleportTo(positions.create(-1, 0, -10))
    builder.face(CompassDirection.South)
    builder.mark()
    builder.move(SixDirection.Forward, 8)
    builder.move(SixDirection.Left, 2)
    builder.move(SixDirection.Back, 8)
    builder.tracePath(blocks.block(Block.Stone))
    builder.move(SixDirection.Right, 1)
    builder.mark()
    builder.place(blocks.blockByName("stone_slab"))
    builder.move(SixDirection.Up, 1)
    builder.place(blocks.block(Block.TNT))
    builder.move(SixDirection.Right, 1)
    builder.mark()
    builder.move(SixDirection.Forward, 2)
    builder.tracePath(blocks.block(Block.Stone))
    builder.mark()
    builder.move(SixDirection.Forward, 6)
    builder.move(SixDirection.Left, 2)
    builder.move(SixDirection.Back, 7)
    builder.tracePath(blocks.block(Block.RedstoneWire))
    builder.shift(-1, 1, -2)
    builder.mark()
    builder.move(SixDirection.Forward, 1)
    builder.tracePath(blocks.block(Block.RedstoneWire))
    builder.shift(4, -1, 0)
    builder.mark()
    builder.move(SixDirection.Forward, 2)
    builder.tracePath(blocks.repeater(CompassDirection.North, 4))
    builder.shift(1, 0, 1)
    builder.place(blocks.lever(LeverPosition.BlockTopPointsSouthWhenOff))
    builder.move(SixDirection.Back, 1)
    builder.place(blocks.block(Block.Stone))
    builder.move(SixDirection.Down, 1)
    builder.place(blocks.block(Block.Water))
    builder.move(SixDirection.Back, 4)
    builder.mark()
    builder.move(SixDirection.Back, 2)
    builder.tracePath(blocks.block(Block.TNT))
})
```

```package
builder
shapes
```