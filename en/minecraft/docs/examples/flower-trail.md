# Flower trail

![Flower trail](/static/mods/flower-trail.jpg)

Flowers spring up behind you. Walk around and see them follow you!

## Try the code:

```blocks
player.onTravelled(TravelMethod.Walk, function () {
    blocks.place(blocks.block(Block.YellowFlower), positions.create(0, 0, 0))
    blocks.place(blocks.block(Block.Poppy), positions.create(0, 0, 0))
    blocks.place(blocks.block(Block.BlueOrchid), positions.create(0, 0, 0))
})
```