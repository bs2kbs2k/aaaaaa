# Activity: Last Stand at the Alamo

## Challenges

### Challenge 1 - Create Cave Spiders

```blocks
mobs.onMobKilled(mobs.monster(MonsterMob.CaveSpider), function () {
    for (let i = 0; i < 5; i++) {
        mobs.spawn(mobs.monster(MonsterMob.CaveSpider), positions.random(
        positions.create(10, 0, 10),
        positions.create(-10, 0, -10)
        ))
    }
})
```

### Challenge 2 - Make a Friendly Zombie Act More Like a Real Zombie

```blocks
mobs.onMobKilled(mobs.monster(MonsterMob.Zombie), function () {
    for (let i = 0; i < 5; i++) {
        mobs.spawn(mobs.monster(MonsterMob.Zombie), positions.random(
        positions.create(10, 0, 10),
        positions.create(-10, 0, -10)
        ))
    }
})
gameplay.setGameMode(
GameMode.Survival,
mobs.target(TargetSelectorKind.LocalPlayer)
)
```

### Challenge 3 - Get Ready for the Horde

```blocks
mobs.onMobKilled(mobs.monster(MonsterMob.Zombie), function () {
    for (let i = 0; i < 5; i++) {
        mobs.spawn(mobs.monster(MonsterMob.Zombie), positions.random(
        positions.create(10, 0, 10),
        positions.create(-10, 0, -10)
        ))
    }
})
player.onChat("z", function () {
    mobs.spawn(mobs.monster(MonsterMob.Zombie), positions.create(20, 0, 0))
    mobs.give(
    mobs.target(TargetSelectorKind.LocalPlayer),
    blocks.item(Item.IronSword),
    1
    )
})
player.onDied(function () {
    mobs.kill(
    mobs.target(TargetSelectorKind.AllEntities)
    )
})
gameplay.setGameMode(
GameMode.Survival,
mobs.target(TargetSelectorKind.LocalPlayer)
)
```

## Experiments

### Experiment 1 - A Ranged Weapon for Your Player

```blocks
mobs.onMobKilled(mobs.monster(MonsterMob.Zombie), function () {
    for (let i = 0; i < 2; i++) {
        mobs.spawn(mobs.monster(MonsterMob.Zombie), positions.random(
        positions.create(10, 0, 10),
        positions.create(-10, 0, -10)
        ))
    }
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
```

### Experiment 2 - The Perfect Zombie Movie

```blocks
mobs.onMobKilled(mobs.monster(MonsterMob.Zombie), function () {
    for (let i = 0; i < 5; i++) {
        mobs.spawn(mobs.monster(MonsterMob.Zombie), positions.random(
        positions.create(10, 0, 10),
        positions.create(-10, 0, -10)
        ))
    }
})
player.onChat("z", function () {
    mobs.spawn(mobs.monster(MonsterMob.Zombie), positions.create(20, 0, 0))
    mobs.give(
    mobs.target(TargetSelectorKind.LocalPlayer),
    blocks.item(Item.Bow),
    1
    )
    mobs.give(
    mobs.target(TargetSelectorKind.LocalPlayer),
    blocks.item(Item.Arrow),
    100
    )
})
player.onDied(function () {
    mobs.kill(
    mobs.target(TargetSelectorKind.AllEntities)
    )
})
gameplay.timeSet(gameplay.time(DayTime.Midnight))
gameplay.setWeather(Weather.Thunder)
gameplay.setGameMode(
GameMode.Survival,
mobs.target(TargetSelectorKind.LocalPlayer)
)
```