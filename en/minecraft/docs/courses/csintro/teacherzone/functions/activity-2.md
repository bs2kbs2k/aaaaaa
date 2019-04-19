# Activity: Zombie Pig

## Challenges

### Challenge 1 - Function to Keep Score

```blocks
let scoreNum = 0
player.onChat("play", function () {
    scoreNum = 0
    atmosphere()
    setup()
    zombiepig()
})
function zombiepig() {
    mobs.spawn(mobs.animal(AnimalMob.Pig), positions.create(0, 0, -5))
    mobs.spawn(mobs.projectile(ProjectileMob.LightningBolt), positions.create(0, 0, -5))
}
mobs.onMobKilled(mobs.monster(MonsterMob.PigZombie), function () {
    zombiepig()
    scoreNum += 1
    Score()
})
function atmosphere() {
    gameplay.timeSet(gameplay.time(DayTime.Midnight))
}
function setup() {
    gameplay.setDifficulty(GameDifficulty.Easy)
    gameplay.setGameMode(
    GameMode.Survival,
    mobs.target(TargetSelectorKind.LocalPlayer)
    )
    mobs.give(
    mobs.target(TargetSelectorKind.LocalPlayer),
    blocks.item(Item.DiamondSword),
    1
    )
}
function Score() {
    player.say("Currently you have " + ("" + scoreNum + " points."))
}
```

![Mini-Game Challenge Complete ](/static/courses/csintro/functions/scoreboard.png)

### Challenge 2 - Function to Randomize Position

```blocks
let RandomPos: Position = null
let scoreNum = 0
player.onChat("play", function () {
    scoreNum = 0
    atmosphere()
    setup()
    zombiepig()
})
function zombiepig() {
    RandomPosition()
    mobs.spawn(mobs.animal(AnimalMob.Pig), RandomPos)
    mobs.spawn(mobs.projectile(ProjectileMob.LightningBolt), RandomPos)
}
mobs.onMobKilled(mobs.monster(MonsterMob.PigZombie), function () {
    zombiepig()
    scoreNum += 1
    Score()
})
function Score() {
    player.say("Currently you have " + ("" + scoreNum + " points."))
}
function setup() {
    gameplay.setDifficulty(GameDifficulty.Easy)
    gameplay.setGameMode(
    GameMode.Survival,
    mobs.target(TargetSelectorKind.LocalPlayer)
    )
    mobs.give(
    mobs.target(TargetSelectorKind.LocalPlayer),
    blocks.item(Item.DiamondSword),
    1
    )
}
function atmosphere() {
    gameplay.timeSet(gameplay.time(DayTime.Midnight))
}
function RandomPosition() {
    RandomPos = positions.create(Math.randomRange(0, 10), 0, Math.randomRange(0, 10))
}
```

![Mini-Game Challenge Complete ](/static/courses/csintro/functions/pigmanchallenge2.jpg)

## Experiments

### Experiment 1 - Lots of Pigmen and Lots of Lightning

```blocks
let Z_Coordinate = 0
let X_Coordinate_Back = 0
let X_Coordinate_Front = 0
player.onChat("pig", function (Command) {
    for (let Number_of_rows = 0; Number_of_rows <= 4; Number_of_rows++) {
        for (let Number_of_pigs_in_row = 0; Number_of_pigs_in_row <= 4; Number_of_pigs_in_row++) {
            X_Coordinate_Front = Number_of_rows
            X_Coordinate_Back = 0 - Number_of_rows
            Z_Coordinate = Number_of_pigs_in_row - 2
            if (Command == 1) {
                mobs.spawn(mobs.animal(AnimalMob.Pig), positions.create(X_Coordinate_Front, 0, Z_Coordinate))
            } else if (Command == 2) {
                mobs.spawn(mobs.animal(AnimalMob.Pig), positions.create(X_Coordinate_Back, 0, Z_Coordinate))
            } else if (Command == 3) {
                mobs.spawn(mobs.projectile(ProjectileMob.LightningBolt), positions.create(X_Coordinate_Front, 0, Z_Coordinate))
                mobs.spawn(mobs.projectile(ProjectileMob.LightningBolt), positions.create(X_Coordinate_Back, 0, Z_Coordinate))
            } else {

            }
        }
    }
    Command += 1
    player.runChatCommandWithArguments("pig", "" + Command)
})
```

### Experiment 2 - Flashlight

```blocks
function TestGround() {
    if (blocks.testForBlock(blocks.block(Block.Grass), positions.create(0, -1, 0))) {
        player.say("Walking on grass")
    }
}
player.onTravelled(TravelMethod.Walk, function () {
    TestGround()
})
gameplay.timeSet(gameplay.time(DayTime.Night))
```