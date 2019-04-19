# Activity: We Built a Zoo

## Challenges

## Challenge 1 - Add more animals to the zoo

```blocks
let animalarray: number[] = []
player.onChat("pen", function () {
    builder.teleportTo(positions.create(50, 0, -50))
    builder.face(CompassDirection.West)
    builder.mark()
    for (let i = 0; i < 4; i++) {
        builder.move(SixDirection.Forward, 100)
        builder.turn(TurnDirection.Left)
    }
    builder.tracePath(blocks.block(Block.OakFence))
})
player.onChat("zoo", function () {
    for (let value of animalarray) {
        mobs.spawn(value, positions.create(3, 0, 0))
        mobs.spawn(value, positions.create(3, 0, 0))
    }
})
animalarray = [mobs.animal(AnimalMob.Chicken), mobs.animal(AnimalMob.Cow), mobs.animal(AnimalMob.Pig), mobs.animal(AnimalMob.Sheep), mobs.animal(AnimalMob.Wolf), mobs.animal(AnimalMob.Villager), mobs.animal(AnimalMob.MushroomCow), mobs.animal(AnimalMob.Squid), mobs.animal(AnimalMob.Rabbit), mobs.animal(AnimalMob.Bat), mobs.animal(AnimalMob.Ocelot), mobs.animal(AnimalMob.Horse), mobs.animal(AnimalMob.Donkey), mobs.animal(AnimalMob.Mule), mobs.animal(AnimalMob.SkeletonHorse), mobs.animal(AnimalMob.ZombieHorse), mobs.animal(AnimalMob.PolarBear), mobs.animal(AnimalMob.Llama), mobs.animal(AnimalMob.Parrot)]

```

### Challenge 2 - Create a second array for animal names

```blocks
let animalnames: string[] = []
let animalarray: number[] = []
let CurrentAnimalNum = 0
player.onChat("pen", function () {
    builder.teleportTo(positions.create(50, 0, -50))
    builder.face(CompassDirection.West)
    builder.mark()
    for (let i = 0; i < 4; i++) {
        builder.move(SixDirection.Forward, 100)
        builder.turn(TurnDirection.Left)
    }
    builder.tracePath(blocks.block(Block.OakFence))
})
player.onChat("zoo", function () {
    CurrentAnimalNum = 0
    for (let value of animalarray) {
        mobs.spawn(value, positions.create(3, 0, 0))
        mobs.spawn(value, positions.create(3, 0, 0))
        player.say(animalnames[CurrentAnimalNum])
        loops.pause(1000)
        CurrentAnimalNum += 1
    }
})
animalarray = [mobs.animal(AnimalMob.Chicken), mobs.animal(AnimalMob.Cow), mobs.animal(AnimalMob.Pig), mobs.animal(AnimalMob.Sheep), mobs.animal(AnimalMob.Wolf), mobs.animal(AnimalMob.Villager), mobs.animal(AnimalMob.MushroomCow), mobs.animal(AnimalMob.Squid), mobs.animal(AnimalMob.Rabbit), mobs.animal(AnimalMob.Bat), mobs.animal(AnimalMob.Ocelot), mobs.animal(AnimalMob.Horse), mobs.animal(AnimalMob.Donkey), mobs.animal(AnimalMob.Mule), mobs.animal(AnimalMob.SkeletonHorse), mobs.animal(AnimalMob.ZombieHorse), mobs.animal(AnimalMob.PolarBear), mobs.animal(AnimalMob.Llama), mobs.animal(AnimalMob.Parrot)]
animalnames = ["Chicken", "Cow", "Pig", "Sheep", "Wolf", "Villager", "MushroomCow", "Squid", "Rabbit", "Bat", "Ocelot", "Horse", "Donkey", "Mule", "SkeletonHorse", "ZombieHorse", "PolarBear", "Llama", "Parrot"]

```

## Experiments

## Experiment 1 - Add a birdhouse, birds only!

```blocks
let birds: number[] = []
let landanimal: number[] = []
let WorldPosition: Position = null
let OneLandAnimal = 0
function birdcage() {
    builder.teleportTo(positions.add(
    WorldPosition,
    positions.create(5, 0, -40)
    ))
    builder.face(CompassDirection.West)
    builder.mark()
    for (let i = 0; i < 10; i++) {
        for (let i = 0; i < 4; i++) {
            builder.move(SixDirection.Forward, 20)
            builder.turn(TurnDirection.Left)
        }
        builder.move(SixDirection.Up, 1)
    }
    builder.tracePath(blocks.block(Block.Glass))
    blocks.fill(
    blocks.block(Block.Glass),
    positions.add(
    WorldPosition,
    positions.create(5, 10, -40)
    ),
    positions.add(
    WorldPosition,
    positions.create(-15, 10, -20)
    ),
    FillOperation.Replace
    )
    for (let OneBird of birds) {
        for (let i = 0; i < 10; i++) {
            mobs.spawn(OneBird, positions.add(
            WorldPosition,
            positions.create(-5, 5, -30)
            ))
            mobs.spawn(OneBird, positions.add(
            WorldPosition,
            positions.create(-5, 5, -30)
            ))
        }
    }
}
function landanimals() {
    builder.teleportTo(positions.add(
    WorldPosition,
    positions.create(5, 0, -5)
    ))
    builder.face(CompassDirection.West)
    builder.mark()
    for (let i = 0; i < 4; i++) {
        builder.move(SixDirection.Forward, 20)
        builder.turn(TurnDirection.Left)
    }
    builder.tracePath(blocks.block(Block.OakFence))
    for (let OneLandAnimal2 of landanimal) {
        mobs.spawn(OneLandAnimal2, positions.add(
        WorldPosition,
        positions.create(3, 0, 0)
        ))
        mobs.spawn(OneLandAnimal2, positions.add(
        WorldPosition,
        positions.create(3, 0, 0)
        ))
    }
}
player.onChat("zoo", function () {
    SaveWorldPosition()
    landanimals()
    birdcage()
})
function SaveWorldPosition() {
    WorldPosition = player.position()
}
OneLandAnimal = 0
landanimal = [mobs.animal(AnimalMob.Cow), mobs.animal(AnimalMob.Pig), mobs.animal(AnimalMob.Sheep), mobs.animal(AnimalMob.Wolf), mobs.animal(AnimalMob.MushroomCow), mobs.animal(AnimalMob.Rabbit), mobs.animal(AnimalMob.Ocelot), mobs.animal(AnimalMob.Horse), mobs.animal(AnimalMob.Donkey), mobs.animal(AnimalMob.Mule), mobs.animal(AnimalMob.SkeletonHorse), mobs.animal(AnimalMob.ZombieHorse), mobs.animal(AnimalMob.PolarBear), mobs.animal(AnimalMob.Llama)]
birds = [mobs.animal(AnimalMob.Parrot), mobs.animal(AnimalMob.Chicken), mobs.animal(AnimalMob.Bat)]

```

## Experiment 2 - Add another zoo exhibit for the squids

```blocks
let UnderwaterAnimal: number[] = []
let birds: number[] = []
let WorldPosition: Position = null
let landanimal: number[] = []
function SquidAquarium() {
    blocks.fill(
    blocks.block(Block.Water),
    positions.add(
    WorldPosition,
    positions.create(5, -1, 30)
    ),
    positions.add(
    WorldPosition,
    positions.create(-15, -3, 60)
    ),
    FillOperation.Replace
    )
    for (let OneWaterAnimal of UnderwaterAnimal) {
        mobs.spawn(OneWaterAnimal, positions.add(
        WorldPosition,
        positions.create(5, 2, 45)
        ))
        mobs.spawn(OneWaterAnimal, positions.add(
        WorldPosition,
        positions.create(5, 2, 45)
        ))
    }
}
function landanimals() {
    builder.teleportTo(positions.add(
    WorldPosition,
    positions.create(5, 0, -5)
    ))
    builder.face(CompassDirection.West)
    builder.mark()
    for (let i = 0; i < 4; i++) {
        builder.move(SixDirection.Forward, 20)
        builder.turn(TurnDirection.Left)
    }
    builder.tracePath(blocks.block(Block.OakFence))
    for (let OneLandAnimal of landanimal) {
        mobs.spawn(OneLandAnimal, positions.add(
        WorldPosition,
        positions.create(3, 0, 0)
        ))
        mobs.spawn(OneLandAnimal, positions.add(
        WorldPosition,
        positions.create(3, 0, 0)
        ))
    }
}
player.onChat("zoo", function () {
    SaveWorldPosition()
    landanimals()
    birdcage()
    SquidAquarium()
})
function SaveWorldPosition() {
    WorldPosition = player.position()
}
function birdcage() {
    builder.teleportTo(positions.add(
    WorldPosition,
    positions.create(5, 0, -40)
    ))
    builder.face(CompassDirection.West)
    builder.mark()
    for (let i = 0; i < 10; i++) {
        for (let i = 0; i < 4; i++) {
            builder.move(SixDirection.Forward, 20)
            builder.turn(TurnDirection.Left)
        }
        builder.move(SixDirection.Up, 1)
    }
    builder.tracePath(blocks.block(Block.Glass))
    blocks.fill(
    blocks.block(Block.Glass),
    positions.add(
    WorldPosition,
    positions.create(5, 10, -40)
    ),
    positions.add(
    WorldPosition,
    positions.create(-15, 10, -20)
    ),
    FillOperation.Replace
    )
    for (let OneBird of birds) {
        for (let i = 0; i < 10; i++) {
            mobs.spawn(OneBird, positions.add(
            WorldPosition,
            positions.create(-5, 5, -30)
            ))
            mobs.spawn(OneBird, positions.add(
            WorldPosition,
            positions.create(-5, 5, -30)
            ))
        }
    }
}
landanimal = [mobs.animal(AnimalMob.Cow), mobs.animal(AnimalMob.Pig), mobs.animal(AnimalMob.Sheep), mobs.animal(AnimalMob.Wolf), mobs.animal(AnimalMob.MushroomCow), mobs.animal(AnimalMob.Rabbit), mobs.animal(AnimalMob.Ocelot), mobs.animal(AnimalMob.Horse), mobs.animal(AnimalMob.Donkey), mobs.animal(AnimalMob.Mule), mobs.animal(AnimalMob.SkeletonHorse), mobs.animal(AnimalMob.ZombieHorse), mobs.animal(AnimalMob.PolarBear), mobs.animal(AnimalMob.Llama)]
birds = [mobs.animal(AnimalMob.Parrot), mobs.animal(AnimalMob.Chicken), mobs.animal(AnimalMob.Bat)]
UnderwaterAnimal = [mobs.animal(AnimalMob.Squid)]


```