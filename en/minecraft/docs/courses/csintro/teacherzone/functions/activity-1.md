# Activity: Leap of Faith Mini-Game

## Challenges

### Challenge 1 - Halloween Platform Jump

```blocks
function pool() {
    blocks.fill(
    blocks.block(Block.Lava),
    positions.create(0, -1, 0),
    positions.create(2, -3, 2),
    FillOperation.Replace
    )
}
function teleport() {
    player.teleport(positions.create(2, 65, 2))
    gameplay.setGameMode(
    GameMode.Survival,
    mobs.target(TargetSelectorKind.LocalPlayer)
    )
}
function Monsters() {
    for (let i = 0; i < 10; i++) {
        mobs.spawn(mobs.monster(MonsterMob.WitherSkeleton), positions.create(0, 0, 0))
    }
}
function platform() {
    blocks.fill(
    blocks.block(Block.DoubleWoodenSlab),
    positions.create(1, 64, 1),
    positions.create(3, 64, 3),
    FillOperation.Replace
    )
}
function Sword() {
    mobs.give(
    mobs.target(TargetSelectorKind.LocalPlayer),
    blocks.item(Item.DiamondSword),
    1
    )
}
pool()
Monsters()
platform()
teleport()
Sword()
```

### Challenge 2 - On Bounce

```blocks
function platform() {
    blocks.fill(
    blocks.block(Block.DoubleWoodenSlab),
    positions.create(1, 64, 1),
    positions.create(3, 64, 3),
    FillOperation.Replace
    )
}
function pool() {
    blocks.fill(
    blocks.block(Block.SlimeBlock),
    positions.create(0, -1, 0),
    positions.create(2, -3, 2),
    FillOperation.Replace
    )
}
function MyNewFunction() {
    blocks.fill(
    blocks.block(Block.OxeyeDaisy),
    positions.create(5, 3, 5),
    positions.create(-5, 4, -5),
    FillOperation.Replace
    )
}
function teleport() {
    player.teleport(positions.create(2, 65, 2))
    gameplay.setGameMode(
    GameMode.Survival,
    mobs.target(TargetSelectorKind.LocalPlayer)
    )
}
player.onTravelled(TravelMethod.Bounce, function () {
    MyNewFunction()
})
pool()
platform()
teleport()
```

## Experiments

### Experiment 1 - Bouncing Pigs

```blocks
player.onTravelled(TravelMethod.Bounce, function () {
    animals()
})
function animals() {
    mobs.spawn(mobs.animal(AnimalMob.Pig), positions.random(
    positions.create(-10, 20, -10),
    positions.create(10, 20, 10)
    ))
}
function slime() {
    blocks.fill(
    blocks.block(Block.SlimeBlock),
    positions.create(-20, 0, -20),
    positions.create(20, 0, 20),
    FillOperation.Replace
    )
}
player.onChat("slime", function () {
    slime()
})
```

### Experiment 2 - Bouncing, Lightning, and Zombie Pigmen

```blocks
player.onChat("slime", function () {
    slime()
})
function slime() {
    blocks.fill(
    blocks.block(Block.SlimeBlock),
    positions.create(-20, 0, -20),
    positions.create(20, 0, 20),
    FillOperation.Replace
    )
}
function zombiepig() {
    mobs.spawn(mobs.animal(AnimalMob.Pig), positions.random(
    positions.create(-10, 20, -10),
    positions.create(10, 20, 10)
    ))
    mobs.spawn(mobs.projectile(ProjectileMob.LightningBolt), positions.random(
    positions.create(-10, 20, -10),
    positions.create(10, 20, 10)
    ))
}
player.onTravelled(TravelMethod.Bounce, function () {
    zombiepig()
})
```