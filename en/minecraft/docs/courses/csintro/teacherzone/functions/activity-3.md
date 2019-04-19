# Activity: Burger

## Challenges

### Challenge 1 - Burger Plate

```blocks
function Tomato() {
    blocks.fill(
    blocks.block(Block.RedConcrete),
    positions.create(4, 4, 4),
    positions.create(7, 4, 7),
    FillOperation.Replace
    )
}
function BottomBun() {
    blocks.fill(
    blocks.block(Block.PlanksOak),
    positions.create(3, 1, 3),
    positions.create(8, 1, 8),
    FillOperation.Replace
    )
}
player.onChat("burger", function () {
    Plate()
    BottomBun()
    Meat()
    Lettuce()
    Tomato()
    TopBun()
})
function Lettuce() {
    blocks.fill(
    blocks.block(Block.LimeConcrete),
    positions.create(4, 3, 4),
    positions.create(7, 3, 7),
    FillOperation.Replace
    )
}
function TopBun() {
    blocks.fill(
    blocks.block(Block.PlanksOak),
    positions.create(3, 5, 3),
    positions.create(8, 5, 8),
    FillOperation.Replace
    )
    blocks.fill(
    blocks.block(Block.PlanksOak),
    positions.create(4, 6, 4),
    positions.create(7, 6, 7),
    FillOperation.Replace
    )
}
function Meat() {
    blocks.fill(
    blocks.block(Block.BrownTerracotta),
    positions.create(4, 2, 4),
    positions.create(7, 2, 7),
    FillOperation.Replace
    )
}
function Plate() {
    blocks.fill(
    blocks.block(Block.WhiteConcrete),
    positions.create(1, 0, 1),
    positions.create(10, 0, 10),
    FillOperation.Replace
    )
}
```

![Complete burger](/static/courses/csintro/functions/burgerplate.jpg)

![Complete burger](/static/courses/csintro/functions/burgerplate2.jpg)

### Challenge 2 - Circular Lettuce

```blocks
function Tomato() {
    blocks.fill(
    blocks.block(Block.RedConcrete),
    positions.create(4, 4, 4),
    positions.create(7, 4, 7),
    FillOperation.Replace
    )
}
function BottomBun() {
    blocks.fill(
    blocks.block(Block.PlanksOak),
    positions.create(3, 1, 3),
    positions.create(8, 1, 8),
    FillOperation.Replace
    )
}
player.onChat("burger", function () {
    Plate()
    BottomBun()
    Meat()
    Lettuce()
    Tomato()
    TopBun()
})
function Lettuce() {
    shapes.circle(
    blocks.block(Block.LimeConcrete),
    positions.create(5, 3, 5),
    4,
    Axis.Y,
    ShapeOperation.Replace
    )
}
function Meat() {
    blocks.fill(
    blocks.block(Block.BrownTerracotta),
    positions.create(4, 2, 4),
    positions.create(7, 2, 7),
    FillOperation.Replace
    )
}
function TopBun() {
    blocks.fill(
    blocks.block(Block.PlanksOak),
    positions.create(3, 5, 3),
    positions.create(8, 5, 8),
    FillOperation.Replace
    )
    blocks.fill(
    blocks.block(Block.PlanksOak),
    positions.create(4, 6, 4),
    positions.create(7, 6, 7),
    FillOperation.Replace
    )
}
function Plate() {
    blocks.fill(
    blocks.block(Block.WhiteConcrete),
    positions.create(1, 0, 1),
    positions.create(10, 0, 10),
    FillOperation.Replace
    )
}
```

![Complete burger](/static/courses/csintro/functions/burgerwithlettuce.jpg)

## Experiments

### Experiment 1 - Bat Cave

```blocks
let bat_cave: Position = null
player.onChat("play", function () {
    cave()
    delay()
    bats()
})
function delay() {
    player.say("You have 10 seconds to go out before the bats arrive!")
    loops.pause(10000)
}
function cave() {
    player.say("dig a cave!")
    gameplay.timeSet(gameplay.time(DayTime.Day))
    for (let i = 0; i < 50; i++) {
        blocks.fill(
        blocks.block(Block.Air),
        positions.create(-1, 0, -1),
        positions.create(1, -3, 1),
        FillOperation.Replace
        )
    }
    bat_cave = player.position()
}
function bats() {
    player.say("Watch for bats!")
    gameplay.timeSet(gameplay.time(DayTime.Dusk))
    for (let i = 0; i < 200; i++) {
        mobs.spawn(mobs.animal(AnimalMob.Bat), bat_cave)
    }
}

```

![Bat Cave](/static/courses/csintro/functions/batcave.jpg) ![Bat Cave](/static/courses/csintro/functions/batcave2.jpg) ![Bat Cave](/static/courses/csintro/functions/batcave3.jpg) ![Bat Cave](/static/courses/csintro/functions/batcave4.jpg)