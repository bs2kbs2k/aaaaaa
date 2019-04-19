# Activity: The Linked Wall

## Challenges

### Challenge 1 - Add More Blocks When Glass Is Broken

```blocks
let to_position: Position = null
let from_position: Position = null
let PlayerPosition: Position = null
player.onChat("position", function () {
    PlayerPosition = player.position()
    from_position = positions.add(
    PlayerPosition,
    positions.create(6, 0, 0)
    )
    to_position = positions.add(
    PlayerPosition,
    positions.create(-6, 13, 0)
    )
})
player.onChat("wall", function () {
    blocks.fill(
    blocks.block(Block.Glass),
    from_position,
    to_position,
    FillOperation.Replace
    )
})
blocks.onBlockBroken(blocks.block(Block.Glass), function () {
    blocks.place(blocks.block(Block.DiamondBlock), positions.random(
    from_position,
    to_position
    ))
    blocks.place(blocks.block(Block.DiamondBlock), positions.random(
    from_position,
    to_position
    ))
    blocks.place(blocks.block(Block.DiamondBlock), positions.random(
    from_position,
    to_position
    ))
})
blocks.onBlockBroken(blocks.block(Block.DiamondBlock), function () {
    blocks.place(blocks.block(Block.OrangeWool), positions.random(
    from_position,
    to_position
    ))
})
```

### Challenge 2 - Instead of Orange Wool, Create Chickens!

```blocks
let to_position: Position = null
let from_position: Position = null
let PlayerPosition: Position = null
player.onChat("position", function () {
    PlayerPosition = player.position()
    from_position = positions.add(
    PlayerPosition,
    positions.create(6, 0, 0)
    )
    to_position = positions.add(
    PlayerPosition,
    positions.create(-6, 13, 0)
    )
})
player.onChat("wall", function () {
    blocks.fill(
    blocks.block(Block.Glass),
    from_position,
    to_position,
    FillOperation.Replace
    )
})
blocks.onBlockBroken(blocks.block(Block.Glass), function () {
    blocks.place(blocks.block(Block.DiamondBlock), positions.random(
    from_position,
    to_position
    ))
    blocks.place(blocks.block(Block.DiamondBlock), positions.random(
    from_position,
    to_position
    ))
    blocks.place(blocks.block(Block.DiamondBlock), positions.random(
    from_position,
    to_position
    ))
})
blocks.onBlockBroken(blocks.block(Block.DiamondBlock), function () {
    for (let i = 0; i < 10; i++) {
        mobs.spawn(mobs.animal(AnimalMob.Chicken), positions.create(0, 2, 0))
    }
})
```

## Experiments

### Experiment 1 - The Colosseum

```blocks
let Monster_Spawn_Position: Position = null
let YourPosition: Position = null
function Cage_Back_Wall() {
    blocks.fill(
    blocks.block(Block.ChiseledStoneBricks),
    positions.add(
    YourPosition,
    positions.create(101, 10, -37)
    ),
    positions.add(
    YourPosition,
    positions.create(-21, 20, -37)
    ),
    FillOperation.Replace
    )
    blocks.fill(
    blocks.block(Block.ChiseledStoneBricks),
    positions.add(
    YourPosition,
    positions.create(101, 10, 37)
    ),
    positions.add(
    YourPosition,
    positions.create(-21, 20, 37)
    ),
    FillOperation.Replace
    )
    blocks.fill(
    blocks.block(Block.ChiseledStoneBricks),
    positions.add(
    YourPosition,
    positions.create(107, 10, 31)
    ),
    positions.add(
    YourPosition,
    positions.create(107, 20, -31)
    ),
    FillOperation.Replace
    )
    blocks.fill(
    blocks.block(Block.ChiseledStoneBricks),
    positions.add(
    YourPosition,
    positions.create(-27, 10, 31)
    ),
    positions.add(
    YourPosition,
    positions.create(-27, 20, -31)
    ),
    FillOperation.Replace
    )
}
mobs.onMobKilled(mobs.monster(MonsterMob.CaveSpider), function () {
    mobs.spawn(mobs.monster(MonsterMob.CaveSpider), positions.add(
    YourPosition,
    positions.create(Math.randomRange(30, 60), 15, 32)
    ))
})
function Print_Words() {
    blocks.print(
    "Cave Spiders",
    blocks.block(Block.BlackGlazedTerracotta),
    positions.add(
    YourPosition,
    positions.create(0, 0, 30)
    ),
    CompassDirection.East
    )
    blocks.print(
    "Ocelots",
    blocks.block(Block.YellowShulkerBox),
    positions.add(
    YourPosition,
    positions.create(20, 0, -30)
    ),
    CompassDirection.East
    )
    blocks.print(
    "Wolves",
    blocks.block(Block.WhiteShulkerBox),
    positions.add(
    YourPosition,
    positions.create(100, 0, 20)
    ),
    CompassDirection.North
    )
    blocks.print(
    "Guardians",
    blocks.block(Block.OrangeShulkerBox),
    positions.add(
    YourPosition,
    positions.create(-20, 0, 25)
    ),
    CompassDirection.North
    )
}
function Spawn_Monsters() {
    Random_Position()
    for (let i = 0; i < 20; i++) {
        mobs.spawn(mobs.monster(MonsterMob.CaveSpider), Monster_Spawn_Position)
    }
    Random_Position()
    for (let i = 0; i < 20; i++) {
        mobs.spawn(mobs.animal(AnimalMob.Ocelot), Monster_Spawn_Position)
    }
    Random_Position()
    for (let i = 0; i < 20; i++) {
        mobs.spawn(mobs.animal(AnimalMob.Wolf), Monster_Spawn_Position)
    }
    Random_Position()
    for (let i = 0; i < 20; i++) {
        mobs.spawn(mobs.monster(MonsterMob.Guardian), Monster_Spawn_Position)
    }
}
mobs.onMobKilled(mobs.animal(AnimalMob.Ocelot), function () {
    mobs.spawn(mobs.animal(AnimalMob.Ocelot), positions.add(
    YourPosition,
    positions.create(Math.randomRange(30, 60), 15, -32)
    ))
})
function Bottom_of_Walls() {
    blocks.fill(
    blocks.block(Block.GrayConcrete),
    positions.add(
    YourPosition,
    positions.create(101, 0, -31)
    ),
    positions.add(
    YourPosition,
    positions.create(-21, 10, -31)
    ),
    FillOperation.Replace
    )
    blocks.fill(
    blocks.block(Block.GrayConcrete),
    positions.add(
    YourPosition,
    positions.create(101, 0, 31)
    ),
    positions.add(
    YourPosition,
    positions.create(-21, 10, 31)
    ),
    FillOperation.Replace
    )
    blocks.fill(
    blocks.block(Block.GrayConcrete),
    positions.add(
    YourPosition,
    positions.create(101, 0, 31)
    ),
    positions.add(
    YourPosition,
    positions.create(101, 10, -31)
    ),
    FillOperation.Replace
    )
    blocks.fill(
    blocks.block(Block.GrayConcrete),
    positions.add(
    YourPosition,
    positions.create(-21, 0, 31)
    ),
    positions.add(
    YourPosition,
    positions.create(-21, 10, -31)
    ),
    FillOperation.Replace
    )
}
function Glass_for_Cage() {
    blocks.fill(
    blocks.block(Block.GlassPane),
    positions.add(
    YourPosition,
    positions.create(101, 10, -31)
    ),
    positions.add(
    YourPosition,
    positions.create(-21, 20, -31)
    ),
    FillOperation.Replace
    )
    blocks.fill(
    blocks.block(Block.GlassPane),
    positions.add(
    YourPosition,
    positions.create(101, 10, 31)
    ),
    positions.add(
    YourPosition,
    positions.create(-21, 20, 31)
    ),
    FillOperation.Replace
    )
    blocks.fill(
    blocks.block(Block.GlassPane),
    positions.add(
    YourPosition,
    positions.create(101, 10, 31)
    ),
    positions.add(
    YourPosition,
    positions.create(101, 20, -31)
    ),
    FillOperation.Replace
    )
    blocks.fill(
    blocks.block(Block.GlassPane),
    positions.add(
    YourPosition,
    positions.create(-21, 10, 31)
    ),
    positions.add(
    YourPosition,
    positions.create(-21, 20, -31)
    ),
    FillOperation.Replace
    )
}
player.onChat("go", function () {
    YourPosition = player.position()
    mobs.give(
    mobs.target(TargetSelectorKind.LocalPlayer),
    blocks.item(Item.DiamondSword),
    1
    )
    Bottom_of_Walls()
    Glass_for_Cage()
    Cage_Back_Wall()
    Cage_Floor()
    Cage_Roof()
    Cage_End_Caps()
    Spawn_Monsters()
    Print_Words()
})
function Cage_Floor() {
    blocks.fill(
    blocks.block(Block.WhiteShulkerBox),
    positions.add(
    YourPosition,
    positions.create(101, 10, -32)
    ),
    positions.add(
    YourPosition,
    positions.create(-21, 10, -37)
    ),
    FillOperation.Replace
    )
    blocks.fill(
    blocks.block(Block.WhiteShulkerBox),
    positions.add(
    YourPosition,
    positions.create(101, 10, 32)
    ),
    positions.add(
    YourPosition,
    positions.create(-21, 10, 37)
    ),
    FillOperation.Replace
    )
    blocks.fill(
    blocks.block(Block.WhiteShulkerBox),
    positions.add(
    YourPosition,
    positions.create(102, 10, 31)
    ),
    positions.add(
    YourPosition,
    positions.create(107, 10, -31)
    ),
    FillOperation.Replace
    )
    blocks.fill(
    blocks.block(Block.WhiteShulkerBox),
    positions.add(
    YourPosition,
    positions.create(-22, 10, 31)
    ),
    positions.add(
    YourPosition,
    positions.create(-27, 10, -31)
    ),
    FillOperation.Replace
    )
}
function Cage_Roof() {
    blocks.fill(
    blocks.block(Block.WhiteShulkerBox),
    positions.add(
    YourPosition,
    positions.create(101, 20, -32)
    ),
    positions.add(
    YourPosition,
    positions.create(-21, 20, -37)
    ),
    FillOperation.Replace
    )
    blocks.fill(
    blocks.block(Block.WhiteShulkerBox),
    positions.add(
    YourPosition,
    positions.create(101, 20, 32)
    ),
    positions.add(
    YourPosition,
    positions.create(-21, 20, 37)
    ),
    FillOperation.Replace
    )
    blocks.fill(
    blocks.block(Block.WhiteShulkerBox),
    positions.add(
    YourPosition,
    positions.create(102, 20, 31)
    ),
    positions.add(
    YourPosition,
    positions.create(107, 20, -31)
    ),
    FillOperation.Replace
    )
    blocks.fill(
    blocks.block(Block.WhiteShulkerBox),
    positions.add(
    YourPosition,
    positions.create(-22, 20, 31)
    ),
    positions.add(
    YourPosition,
    positions.create(-27, 20, -31)
    ),
    FillOperation.Replace
    )
}
function Cage_End_Caps() {
    blocks.fill(
    blocks.block(Block.MagmaBlock),
    positions.add(
    YourPosition,
    positions.create(101, 10, -31)
    ),
    positions.add(
    YourPosition,
    positions.create(107, 20, -37)
    ),
    FillOperation.Replace
    )
    blocks.fill(
    blocks.block(Block.MagmaBlock),
    positions.add(
    YourPosition,
    positions.create(101, 10, 31)
    ),
    positions.add(
    YourPosition,
    positions.create(107, 20, 37)
    ),
    FillOperation.Replace
    )
    blocks.fill(
    blocks.block(Block.MagmaBlock),
    positions.add(
    YourPosition,
    positions.create(-21, 10, -31)
    ),
    positions.add(
    YourPosition,
    positions.create(-27, 20, -37)
    ),
    FillOperation.Replace
    )
    blocks.fill(
    blocks.block(Block.MagmaBlock),
    positions.add(
    YourPosition,
    positions.create(-21, 10, 31)
    ),
    positions.add(
    YourPosition,
    positions.create(-27, 20, 37)
    ),
    FillOperation.Replace
    )
}
mobs.onMobKilled(mobs.animal(AnimalMob.Wolf), function () {
    mobs.spawn(mobs.animal(AnimalMob.Wolf), positions.add(
    YourPosition,
    positions.create(103, 15, Math.randomRange(-10, 10))
    ))
})
mobs.onMobKilled(mobs.monster(MonsterMob.Guardian), function () {
    mobs.spawn(mobs.monster(MonsterMob.Guardian), positions.add(
    YourPosition,
    positions.create(-23, 15, Math.randomRange(-10, 10))
    ))
})
function Random_Position() {
    Monster_Spawn_Position = positions.random(
    positions.add(
    YourPosition,
    positions.create(101, 0, -31)
    ),
    positions.add(
    YourPosition,
    positions.create(-21, 0, 31)
    )
    )
}
```

Other constructive reference examples:

* [Walk on Water](/examples/walk-on-water)

Other destructive reference examples:

* [Game Over](/examples/game-over)
* [Wipe Out](examples/wipe-out)