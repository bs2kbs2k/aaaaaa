# Activity: Arrow Counter

## Challenges

### Challenge 1 - Modify the Message and Track 10 Arrows

```blocks
let arrows = 0
player.onArrowShot(function () {
    arrows += -1
    player.say("Arrows Remaining: " + arrows)
})
arrows = 10
```

### Challenge 2 - Provide a Message When a Player Runs Out of Arrows

```blocks
let arrows = 0
player.onArrowShot(function () {
    arrows += -1
    player.say("Arrows Remaining: " + arrows)
    if (arrows == 0) {
        player.say("Change Players")
    }
})
arrows = 10
```

## Experiments

### Experiment 1 - A Full Target Practice Experience

```blocks
let arrows = 0
player.onArrowShot(function () {
    arrows += 1
    player.say("Arrows Shot: " + (64 - arrows))
})
mobs.give(
mobs.target(TargetSelectorKind.LocalPlayer),
blocks.item(Item.Bow),
1
)
mobs.give(
mobs.target(TargetSelectorKind.LocalPlayer),
blocks.item(Item.Arrow),
64
)
gameplay.setGameMode(
GameMode.Survival,
mobs.target(TargetSelectorKind.LocalPlayer)
)
for (let i = 0; i < 32; i++) {
    mobs.spawn(mobs.animal(AnimalMob.Rabbit), positions.random(
    positions.create(10, 0, 10),
    positions.create(-10, 0, -10)
    ))
}
```

![change game mode](/static/courses/csintro/variables/changinggamemodearrows.jpg) ![spawn rabbits on go](/static/courses/csintro/variables/spawningrabbits32.jpg) ![automate player inventory](/static/courses/csintro/variables/arrowsshotRabbits.jpg)

### Experiment 2 - A Counter to Track the Number of Rabbits Hit

```blocks
let score = 0
let arrows = 0
player.onArrowShot(function () {
    arrows += 1
    player.say("Arrows Remaining: " + (64 - arrows))
})
mobs.onMobKilled(mobs.animal(AnimalMob.Rabbit), function () {
    score += 1
    player.say("Rabbit Hits: " + score)
})
player.onChat("go", function () {
    gameplay.setGameMode(
    GameMode.Survival,
    mobs.target(TargetSelectorKind.LocalPlayer)
    )
    gameplay.setDifficulty(GameDifficulty.Easy)
    mobs.give(
    mobs.target(TargetSelectorKind.NearestPlayer),
    blocks.item(Item.Bow),
    1
    )
    mobs.give(
    mobs.target(TargetSelectorKind.NearestPlayer),
    blocks.item(Item.Arrow),
    64
    )
    for (let i = 0; i < 32; i++) {
        mobs.spawn(mobs.animal(AnimalMob.Rabbit), positions.random(
        positions.create(-5, 0, -5),
        positions.create(5, 0, 5)
        ))
    }
})
```

![rabbit hit counter](/static/courses/csintro/variables/rabbits-hit.jpg)