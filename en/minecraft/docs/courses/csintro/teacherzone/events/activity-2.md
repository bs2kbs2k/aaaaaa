# Activity: Sing a Song of Sixpence

## Challenges

### Challenge 1 - Make Ocelots Appear

```blocks
blocks.onBlockBroken(blocks.block(Block.Grass), function () {
    for (let i = 0; i < 5; i++) {
        mobs.spawn(mobs.animal(AnimalMob.Ocelot), positions.create(0, 1, 0))
    }
})
```

### Challenge 2 - Print "Broken" in TNT

```blocks
blocks.onBlockBroken(blocks.block(Block.Grass), function () {
    blocks.print(
    "Broken",
    blocks.block(Block.TNT),
    positions.create(20, 0, 0),
    CompassDirection.West
    )
})
```

## Experiments

### Experiment 1 - AutoCake

```blocks
blocks.onBlockBroken(blocks.block(Block.Cake), function () {
    for (let i = 0; i < 24; i++) {
        mobs.spawn(mobs.animal(AnimalMob.Parrot), positions.create(0, 2, 0))
    }
})
mobs.give(
mobs.target(TargetSelectorKind.LocalPlayer),
blocks.block(Block.Cake),
1
)
```

### Experiment 2 - Chained Events

```blocks
blocks.onBlockBroken(blocks.block(Block.Cake), function () {
    for (let i = 0; i < 24; i++) {
        mobs.spawn(mobs.animal(AnimalMob.Parrot), positions.create(0, 2, 0))
    }
})
mobs.onMobKilled(mobs.animal(AnimalMob.Parrot), function () {
    for (let i = 0; i < 5; i++) {
        mobs.spawn(mobs.animal(AnimalMob.SkeletonHorse), positions.create(10, 0, 0))
    }
})
mobs.give(
mobs.target(TargetSelectorKind.LocalPlayer),
blocks.block(Block.Cake),
3
)
```