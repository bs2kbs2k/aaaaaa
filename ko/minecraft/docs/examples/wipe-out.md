# Wipe Out

![Earth is wiping away](/static/mods/wipe-out.jpg)

Well, this is a block fill that isn't a fill.

### ~ hint

**GRIEFING ALERT**

This mod will grief your world badly!

### ~

## Try the code:

```blocks
player.onChat("wipeout", function () {
    blocks.fill(
        blocks.block(Block.Air),
        positions.create(-50, 0, -50),
        positions.create(50, 50, 50)
        )
})
```