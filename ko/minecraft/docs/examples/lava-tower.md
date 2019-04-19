# 용암 타워

![Hot lava forms a tower](/static/mods/lava-tower.jpg)

You can always get a lava tower when you need one.

## Try the code:

```blocks
player.onChat("tower", function () {
    blocks.place(blocks.block(Block.Lava), positions.create(5, 20, 0))
    blocks.place(blocks.block(Block.Water), positions.create(5, 135, 0))
    loops.pause(625)
    blocks.place(blocks.block(Block.Air), positions.create(5, 135, 0))
})
```