# Earthquake

![Big crack in the earth](/static/mods/earthquake.jpg)

Disaster at your command!

### ~ hint

GRIEFING ALERT

This mod will grief your world badly. Ask your friends before griefing their worlds.

### ~

## Try the code:

```blocks
player.onChat("earthquake", function () {
    let pos = positions.add(
        player.position(),
        positions.create(-30, 0, 0)
    );
    for (let i = 0; i < 30; i++) {
        pos = positions.add(pos, positions.create(1, 0, Math.randomRange(0, 2)))
        blocks.fill(blocks.block(Block.Air),
            positions.add(pos, positions.create(0, 0, -1)),
            positions.add(pos, positions.create(0, -4, 1))
        )
        blocks.place(blocks.block(Block.Lava), positions.add(pos, positions.create(0, -3, 0)))
    }
})
```