# Activity: Introduction to the Agent

## Challenges

### Challenge 1 - Make the Agent Fly

```blocks
player.onChat("tp", function () {
    agent.teleportToPlayer()
})
player.onChat("fd", function () {
    agent.move(SixDirection.Forward, 1)
})
player.onChat("up", function () {
    agent.move(SixDirection.Up, 1)
})
player.onChat("bk", function () {
    agent.move(SixDirection.Back, 1)
})
player.onChat("dn", function () {
    agent.move(SixDirection.Down, 1)
})
player.onChat("lt", function () {
    agent.turn(TurnDirection.Left)
})
player.onChat("rt", function () {
    agent.turn(TurnDirection.Right)
})
```

### Challenge 2 - Move Your Agent a Set Distance

```blocks
player.onChat("move", function () {
    agent.move(SixDirection.Forward, 4)
    agent.turn(TurnDirection.Right)
    agent.move(SixDirection.Back, 6)
})
```

## Experiments

### Experiment 1 - Fire Walk... I Said NOW, Agent!

```blocks
let Block_Type = 0
let Movement_Number = 0
player.onChat("course", function () {
    for (let index = 0; index <= 1; index++) {
        if (index == 0) {
            Block_Type = blocks.block(Block.RedstoneBlock)
        } else {
            Block_Type = blocks.block(Block.Fire)
        }
        blocks.fill(
        Block_Type,
        positions.create(2, index, -2),
        positions.create(15, index, -2),
        FillOperation.Replace
        )
        blocks.fill(
        Block_Type,
        positions.create(2, index, 2),
        positions.create(10, index, 2),
        FillOperation.Replace
        )
        blocks.fill(
        Block_Type,
        positions.create(15, index, -2),
        positions.create(15, index, 15),
        FillOperation.Replace
        )
        blocks.fill(
        Block_Type,
        positions.create(10, index, 2),
        positions.create(10, index, 10),
        FillOperation.Replace
        )
        blocks.fill(
        Block_Type,
        positions.create(15, index, 15),
        positions.create(2, index, 15),
        FillOperation.Replace
        )
        blocks.fill(
        Block_Type,
        positions.create(10, index, 10),
        positions.create(2, index, 10),
        FillOperation.Replace
        )
    }
})
player.onChat("bk", function (Movement_Number) {
    agent.move(SixDirection.Back, Movement_Number)
})
player.onChat("fd", function (Movement_Number) {
    agent.move(SixDirection.Forward, Movement_Number)
})
player.onChat("tp", function () {
    agent.teleportToPlayer()
})
player.onChat("around", function () {
    for (let i = 0; i < 2; i++) {
        agent.turn(TurnDirection.Right)
    }
})
player.onChat("lt", function () {
    agent.turn(TurnDirection.Left)
})
player.onChat("rt", function () {
    agent.turn(TurnDirection.Right)
})
```

### Experiment 2 - You Can't Contain This Agent!

```blocks
player.onChat("contain", function () {
    blocks.fill(
    blocks.block(Block.LimeStainedGlass),
    positions.create(5, 0, 5),
    positions.create(7, 2, 7),
    FillOperation.Replace
    )
    blocks.place(blocks.block(Block.Air), positions.create(6, 0, 6))
    blocks.place(blocks.block(Block.Air), positions.create(6, 1, 6))
    player.teleport(positions.create(6, 0, 6))
    agent.teleportToPlayer()
    player.teleport(positions.create(-6, 0, -6))
})
player.onChat("break", function () {
    agent.move(SixDirection.Up, 2)
    agent.destroy(SixDirection.Up)
    agent.move(SixDirection.Up, 3)
    agent.destroy(SixDirection.Up)
})
```