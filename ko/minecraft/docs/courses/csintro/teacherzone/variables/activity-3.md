# Activity: Fall Is in the Air

## Challenges

### Challenge 1 - Let's Report in Blocks

```blocks
let fall = 0
let report = 0
player.onChat("cr", function () {
    gameplay.setGameMode(
    GameMode.Creative,
    mobs.target(TargetSelectorKind.LocalPlayer)
    )
})
player.onDied(function () {
    report = fall
    fall = 0
})
player.onChat("su", function () {
    gameplay.setGameMode(
    GameMode.Survival,
    mobs.target(TargetSelectorKind.LocalPlayer)
    )
})
player.onTravelled(TravelMethod.Fall, function () {
    fall += 1
})
player.onChat("pm", function () {
    blocks.print(
    "You fell " + report + " blocks",
    blocks.block(Block.MagmaBlock),
    positions.create(-5, 0, 0),
    CompassDirection.West
    )
})
```

![write death report with blocks](/static/courses/csintro/variables/write-death-report-with-blocks.png)

### Challenge 2 - Set Up a Variable to Track Total Fall Distance over Multiple Falls

```blocks
let TotalFallDistance = 0
let fall = 0
let report = 0
player.onChat("cr", function () {
    gameplay.setGameMode(
    GameMode.Creative,
    mobs.target(TargetSelectorKind.LocalPlayer)
    )
})
player.onChat("su", function () {
    gameplay.setGameMode(
    GameMode.Survival,
    mobs.target(TargetSelectorKind.LocalPlayer)
    )
})
player.onDied(function () {
    report = fall
    TotalFallDistance = TotalFallDistance + fall
    fall = 0
})
player.onTravelled(TravelMethod.Fall, function () {
    fall += 1
})
player.onChat("pm", function () {
    player.say("You fell " + report + " blocks")
})
player.onChat("tot", function () {
    player.say("You have fallen " + TotalFallDistance + " blocks total so far!  Keep Jumping!")
})
```

## Experiments

### Experiment 1 - Track Swim Distance

```blocks
let swim = 0
let fall = 0
let report = 0
player.onChat("cr", function () {
    gameplay.setGameMode(
    GameMode.Creative,
    mobs.target(TargetSelectorKind.LocalPlayer)
    )
})
player.onChat("su", function () {
    gameplay.setGameMode(
    GameMode.Survival,
    mobs.target(TargetSelectorKind.LocalPlayer)
    )
})
player.onDied(function () {
    report = fall
    fall = 0
})
player.onTravelled(TravelMethod.Fall, function () {
    fall += 1
})
player.onChat("pm", function () {
    player.say("You fell " + report + " blocks")
})
player.onTravelled(TravelMethod.SwimWater, function () {
    swim += 1
    player.say("You swam:" + (swim + 1) + " blocks")
})
```