# Activity: Yellow Brick Road

## Challenges

### Challenge 1 - Create a Diamond Ceiling

```blocks
player.onTravelled(TravelMethod.Walk, function () {
    blocks.place(blocks.block(Block.GoldBlock), positions.create(0, -1, 0))
})
```

### Challenge 2 - Build While Flying

```blocks
player.onTravelled(TravelMethod.Fly, function () {
    blocks.fill(
    blocks.block(Block.Stone),
    positions.create(-2, -2, -2),
    positions.create(0, 0, 0),
    FillOperation.Replace
    )
})
```

## Experiments

### Experiment 1 - Magic Carpet Ride

```blocks
player.onTravelled(TravelMethod.Fly, function () {
    blocks.fill(
    blocks.block(Block.SeaLantern),
    positions.create(-3, -1, -3),
    positions.create(3, -1, 3),
    FillOperation.Replace
    )
})
player.onTravelled(TravelMethod.Walk, function () {
    blocks.fill(
    blocks.block(Block.SeaLantern),
    positions.create(-3, -1, -3),
    positions.create(3, -1, 3),
    FillOperation.Replace
    )
})
```

![magic carpet effect](/static/courses/csintro/events/magiccarpet.jpg)

### Experiment 2 - Magic Carpet Artistic Appeal

```blocks
player.onTravelled(TravelMethod.Fly, function () {
    blocks.fill(
    blocks.block(Block.PinkStainedGlassPane),
    positions.create(-3, -1, -3),
    positions.create(3, -1, 3),
    FillOperation.Replace
    )
})
player.onTravelled(TravelMethod.Walk, function () {
    blocks.fill(
    blocks.block(Block.MagentaStainedGlassPane),
    positions.create(-3, -1, -3),
    positions.create(3, -1, 3),
    FillOperation.Replace
    )
})
```

![magic carpet effect](/static/courses/csintro/events/magiccarpet2.jpg)