# Grid world

![Earth dug out in a grid pattern](/static/mods/grid-world.jpg)

The world is getting organized, kind of.

## Try the code:

```blocks
player.onChat("grid", function () {
    for (let index = 0; index < 20; index++) {
        let x = index * 3;
        blocks.fill(blocks.block(Block.Air), positions.create(x, -4, 0), positions.create(x, 5, 60))
        blocks.fill(blocks.block(Block.Air), positions.create(0, -4, x), positions.create(60, 5, x))
    }
})
```