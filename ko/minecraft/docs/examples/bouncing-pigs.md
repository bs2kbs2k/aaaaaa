# 돼지가 떨어진다

![Pigs bouncing in the air](/static/mods/bouncing-pigs.jpg)

Each time you bounce, the game spawns a new pig!

## Try the code:

```blocks
player.onChat("slime", function () {
    blocks.fill(
    blocks.block(Block.SlimeBlock),
    positions.create(-20, 0, -20),
    positions.create(20, 0, 20),
    FillOperation.Replace
    )
})
player.onTravelled(TravelMethod.Bounce, function () {
    mobs.spawn(mobs.animal(AnimalMob.Pig), positions.random(
    positions.create(-10, 20, -10),
    positions.create(10, 20, 10)
    ))
})
```