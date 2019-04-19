# Activity: Auto-farmer

## Challenges

### Challenge 1 - Spawn Some Polar Bears Randomly

```blocks
player.onTravelled(TravelMethod.Walk, function () {
    mobs.spawn(mobs.animal(AnimalMob.PolarBear), positions.random(
    positions.create(4, 0, -10),
    positions.create(10, 0, 10)
    ))
})
```

### Challenge 2 - Build a Protective Cage

```blocks
player.onTravelled(TravelMethod.Walk, function () {
    mobs.spawn(mobs.animal(AnimalMob.PolarBear), positions.random(
    positions.create(4, 0, -10),
    positions.create(10, 0, 10)
    ))
})
player.onTravelled(TravelMethod.Sneak, function () {
    blocks.fill(
    blocks.block(Block.NetherBrickFence),
    positions.create(4, 0, 4),
    positions.create(-4, 4, 4),
    FillOperation.Replace
    )
    blocks.fill(
    blocks.block(Block.BirchFence),
    positions.create(-4, 0, -4),
    positions.create(-4, 4, 4),
    FillOperation.Replace
    )
    blocks.fill(
    blocks.block(Block.AcaciaFence),
    positions.create(4, 0, -4),
    positions.create(4, 4, 4),
    FillOperation.Replace
    )
    blocks.fill(
    blocks.block(Block.SpruceFence),
    positions.create(4, 0, -4),
    positions.create(-4, 4, -4),
    FillOperation.Replace
    )
})
```

## Experiments

### Experiment 1 - Maze-builder

```blocks
let World_Position_at_Start: Position = null
function MazePiece() {
    blocks.fill(
    blocks.block(Block.RedMushroomBlock),
    positions.add(
    World_Position_at_Start,
    positions.createWorld(-2, 0, 0)
    ),
    positions.add(
    World_Position_at_Start,
    positions.createWorld(-2, 4, 14)
    ),
    FillOperation.Replace
    )
    blocks.fill(
    blocks.block(Block.MelonBlock),
    positions.add(
    World_Position_at_Start,
    positions.create(2, 0, 0)
    ),
    positions.add(
    World_Position_at_Start,
    positions.create(2, 4, 4)
    ),
    FillOperation.Replace
    )
    blocks.fill(
    blocks.block(Block.Netherrack),
    positions.add(
    World_Position_at_Start,
    positions.create(6, 0, 8)
    ),
    positions.add(
    World_Position_at_Start,
    positions.create(-2, 4, 8)
    ),
    FillOperation.Replace
    )
    blocks.fill(
    blocks.block(Block.Mushroom15),
    positions.add(
    World_Position_at_Start,
    positions.create(2, 0, 4)
    ),
    positions.add(
    World_Position_at_Start,
    positions.create(6, 4, 4)
    ),
    FillOperation.Replace
    )
    blocks.fill(
    blocks.block(Block.Beacon),
    positions.add(
    World_Position_at_Start,
    positions.create(6, 0, 4)
    ),
    positions.add(
    World_Position_at_Start,
    positions.create(11, 4, 4)
    ),
    FillOperation.Replace
    )
    blocks.fill(
    blocks.block(Block.JackOLantern),
    positions.add(
    World_Position_at_Start,
    positions.create(11, 0, 4)
    ),
    positions.add(
    World_Position_at_Start,
    positions.create(11, 4, 14)
    ),
    FillOperation.Replace
    )
    blocks.fill(
    blocks.block(Block.DiamondOre),
    positions.add(
    World_Position_at_Start,
    positions.create(2, 0, 14)
    ),
    positions.add(
    World_Position_at_Start,
    positions.create(11, 4, 14)
    ),
    FillOperation.Replace
    )
    World_Position_at_Start = positions.add(
    World_Position_at_Start,
    positions.create(0, 0, 14)
    )
}
player.onChat("ms", function () {
    World_Position_at_Start = player.position()
})
player.onTravelled(TravelMethod.Sprint, function () {
    MazePiece()
})
```