# Bat Cave

![Bats flying in a cave](/static/mods/bat-cave.jpg)

Dig a cave and fill it up with bats!

## Try the code:

```blocks
let bat_cave: Position = null
player.onChat("cave", function () {
    player.say("dig a cave!")
    gameplay.timeSet(gameplay.time(DayTime.Day))
    for (let i = 0; i < 50; i++) {
        blocks.fill(
            blocks.block(Block.Air),
            positions.create(-1, 0, -1),
            positions.create(1, 2, 1),
            FillOperation.Replace
        )
    }
    bat_cave = player.position()
    player.say("You have 10 seconds to go out before the bats arrive!")
    loops.pause(10000)
    player.say("Watch for bats!")
    gameplay.timeSet(gameplay.time(DayTime.Dusk))
    for (let i = 0; i < 200; i++) {
        mobs.spawn(mobs.animal(AnimalMob.Bat), bat_cave)
    }
})
```