# Super Digger

![Long tunnel through the earth](/static/mods/super-digger.jpg)

You can tunnel through earth with this command.

## Try the code:

```blocks
player.onChat("dig", function () {
    while (true) {
        blocks.fill(
            blocks.block(Block.Air),
            positions.create(-5, -5, -5),
            positions.create(5, 5, 5),
            FillOperation.Replace
        )
    }
})
```