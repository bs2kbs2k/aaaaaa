# 좀비 돼지

![A zombie pig](/static/mods/zombie-pig.jpg)

Did you know pigs turned into zombies when the are hit by lightning? Let's see it happen!

## Try the code:

```blocks
player.onChat("zombiepig", function () {
    mobs.spawn(mobs.animal(AnimalMob.Pig), positions.create(5, 0, 0))
    mobs.spawn(mobs.projectile(ProjectileMob.LightningBolt), positions.create(5, 0, 0))
})
```