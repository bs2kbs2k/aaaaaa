# Gladiator

![Gladiator game](/static/mods/gladiator.jpg)

The good mobs and the bad mobs meet each other in the arena.

## Try the code:

```blocks
let bad: number[] = []
let good: number[] = []
let index = 0
player.onChat("arena", function () {
    builder.mark()
    for (let i = 0; i < 4; i++) {
        builder.move(SixDirection.Forward, 20)
        builder.turn(TurnDirection.Left)
    }
    builder.raiseWall(blocks.block(Block.PolishedAndesite), 5)
})
player.onChat("spawn", function () {
    for (let index = 0; index <= good.length; index++) {
        mobs.spawn(good[index], positions.create(5, 0, index))
    }
    for (let index = 0; index <= bad.length; index++) {
        mobs.spawn(bad[index], positions.create(5, 0, index))
    }
})
good = [
    mobs.animal(AnimalMob.Chicken), mobs.animal(AnimalMob.Cow), mobs.animal(AnimalMob.Pig),
    mobs.animal(AnimalMob.Sheep), mobs.animal(AnimalMob.Wolf), mobs.animal(AnimalMob.Villager),
    mobs.animal(AnimalMob.MushroomCow), mobs.animal(AnimalMob.Squid), mobs.animal(AnimalMob.Rabbit),
    mobs.animal(AnimalMob.Bat), mobs.animal(AnimalMob.Ocelot), mobs.animal(AnimalMob.Horse)
]
bad = [
    mobs.monster(MonsterMob.Creeper), mobs.monster(MonsterMob.Skeleton), mobs.monster(MonsterMob.Zombie),
    mobs.monster(MonsterMob.Spider), mobs.monster(MonsterMob.PigZombie), mobs.monster(MonsterMob.Slime),
    mobs.monster(MonsterMob.Enderman), mobs.monster(MonsterMob.Silverfish), mobs.monster(MonsterMob.CaveSpider),
    mobs.monster(MonsterMob.Ghast), mobs.monster(MonsterMob.LavaSlime), mobs.monster(MonsterMob.Blaze)
]
```