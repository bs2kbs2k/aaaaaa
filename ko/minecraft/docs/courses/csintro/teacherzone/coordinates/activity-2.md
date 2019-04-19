# Activity: Minecraft Moving Company

## Challenges

### Challenge 1 - Cut and Paste Structures

```blocks
let stop: Position = null
let start: Position = null
player.onChat("start", function () {
    start = player.position()
    player.say("Starting Point Set: " + start)
})
player.onChat("cut", function () {
    blocks.clone(
    start,
    stop,
    positions.create(0, 0, 0),
    CloneMask.Replace,
    CloneMode.Move
    )
})
player.onChat("stop", function () {
    stop = player.position()
    player.say("Stopping Point Set: " + stop)
})
```

![before cut](/static/courses/csintro/coordinates/cutbefore.jpg)

![after cut](/static/courses/csintro/coordinates/cutafter2.jpg)

![after cut](/static/courses/csintro/coordinates/cutafter.jpg)

### Challenge 2 - Move Only the Tree Trunk

```blocks
let stop: Position = null
let start: Position = null
player.onChat("copy", function () {
    blocks.cloneFiltered(
    start,
    stop,
    positions.create(0, 0, 0),
    blocks.block(Block.LogOak),
    CloneMode.Move
    )
})
player.onChat("start", function () {
    start = player.position()
    player.say("Starting Point Set: " + start)
})
player.onChat("stop", function () {
    stop = player.position()
    player.say("Stopping Point Set: " + stop)
})
```

![before copy](/static/courses/csintro/coordinates/move-tree-before.jpg)

![after copy](/static/courses/csintro/coordinates/move-tree-after.jpg)

## Experiments

### Experiment 1 - Walk Through Walls

```blocks
player.onTravelled(TravelMethod.Walk, function () {
    blocks.fill(
    blocks.block(Block.Air),
    positions.create(-2, 0, -2),
    positions.create(2, 3, 2),
    FillOperation.Replace
    )
})
```

![replace with air before](/static/courses/csintro/coordinates/replace-with-air-before.jpg)

![replace with air after1](/static/courses/csintro/coordinates/replace-with-air-after1.jpg)

![replace with air after2](/static/courses/csintro/coordinates/replace-with-air-after2.jpg)