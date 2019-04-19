# Pitfall

![A void opens below the player](/static/mods/pitfall.jpg)

The bottom drops out, seriously! Air is just too thin.

### ~ hint

**GRIEFING ALERT**

This mod will grief your world badly. Ask your friends before griefing their worlds.

### ~

## Try the code:

```blocks
player.onChat("pitfall", function () {
    for(let i = 0; i < 10; i++)
        blocks.fill(blocks.block(Block.Air), positions.create(0, -5, 0), positions.create(0,-1,0))
})
```