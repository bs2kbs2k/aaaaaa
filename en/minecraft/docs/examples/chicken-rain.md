# Chicken Rain

![Chickens falling](/static/mods/chickenrain.jpg)

Chickens and more chickens are falling down!

## Try the code:

```blocks
player.onChat("chicken", function () {
    for (let i = 0; i < 100; i++) {
        mobs.spawn(mobs.animal(AnimalMob.Chicken), positions.create(0, 10, 0))
    }
})
```