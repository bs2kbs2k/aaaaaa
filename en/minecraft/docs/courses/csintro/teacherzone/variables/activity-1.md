# Activity: Chicken Storm

## Challenges

### Challenge 1 - Rename num1 to Something More Meaningful

```blocks
player.onChat("chickens", function (ChickenNum) {
    for (let i = 0; i < ChickenNum; i++) {
        mobs.spawn(mobs.animal(AnimalMob.Chicken), positions.create(0, 10, 0))
    }
})
```

### Challenge 2 - Give Feedback

```blocks
player.onChat("chickens", function (ChickenNum) {
    player.say("" + ChickenNum + " chickens! Coming right up!")
    for (let i = 0; i < ChickenNum; i++) {
        mobs.spawn(mobs.animal(AnimalMob.Chicken), positions.create(0, 10, 0))
    }
})
```

## Experiments

### Experiment 1 - Default Chicken Value

```blocks
player.onChat("chickens", function (ChickenNum) {
    if (ChickenNum == 0) {
        ChickenNum = 2
    }
    for (let i = 0; i < ChickenNum; i++) {
        mobs.spawn(mobs.animal(AnimalMob.Chicken), positions.create(0, 10, 0))
    }
})
```

**Shared Program:** https://makecode.com/_08WV7RPa53qw

## Experiment 2 - Chicken Storm

```blocks
player.onChat("chickens", function (num1) {
    if (num1 == 0) {
        num1 = 2
    }
    for (let i = 0; i < num1; i++) {
        mobs.spawn(mobs.animal(AnimalMob.Chicken), positions.random(
        positions.create(10, 10, 10),
        positions.create(-10, 15, -10)
        ))
    }
})
```

**Shared Program:** https://makecode.com/_HpD1L6LemCVu