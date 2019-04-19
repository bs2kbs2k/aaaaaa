# 토끼 침공

![Rabbits multiplying](/static/mods/rabbit-invasion.jpg)

Make a rabbit and try to get rid of it. Won't happen, two more new rabbits appear each time one gets killed!

## Try the code:

```blocks
player.onChat("rabbit", function () {
    mobs.spawn(mobs.animal(AnimalMob.Rabbit), positions.create(0, 0, 0))
})
mobs.onMobKilled(mobs.animal(AnimalMob.Rabbit), function () {
    for (let i = 0; i < 2; i++) {
        mobs.spawn(mobs.animal(AnimalMob.Rabbit), positions.random(
        positions.create(-5, 0, -5),
        positions.create(5, 0, 5)
        ))
    }
})
```