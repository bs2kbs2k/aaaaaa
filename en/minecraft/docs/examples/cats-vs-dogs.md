# Rain cats and dogs

![Cats and dogs dropping from the sky](/static/mods/cats-vs-dogs.jpg)

The weather changed and it's raining cats and dogs! Cats and dogs fall from the sky with the rain!

## Try the code:

```blocks
player.onChat("rain", function (amount) {
    gameplay.setWeather(Weather.Rain)
    for (let i = 0; i < amount; i++) {
        mobs.spawn(mobs.animal(AnimalMob.Ocelot), positions.random(
        positions.create(10, 5, 10),
        positions.create(-10, 5, -10)
        ))
        mobs.spawn(mobs.animal(AnimalMob.Wolf), positions.random(
        positions.create(10, 5, 10),
        positions.create(-10, 5, -10)
        ))
    }
})
```