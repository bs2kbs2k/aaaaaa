# Activity: All Mine!

## Challenges

### Challenge 1 - Set Up Conditions

```blocks
player.onChat("do", function (AgentOrder) {
    if (AgentOrder == 1) {
        agent.teleportToPlayer()
    } else if (AgentOrder == 2) {
        agent.turn(TurnDirection.Left)
    } else {
        player.say("Enter 1 to teleport or 2 to turn")
    }
})
player.onChat("dig", function () {
    for (let i = 0; i < 2; i++) {
        for (let i = 0; i < 64; i++) {
            if (agent.inspect(AgentInspection.Block, SixDirection.Forward) == blocks.block(Block.DiamondOre)) {
                player.say("We’re rich!")
                agent.destroy(SixDirection.Forward)
                agent.move(SixDirection.Forward, 1)
                agent.collectAll()
            } else {
                agent.destroy(SixDirection.Forward)
                agent.move(SixDirection.Forward, 1)
            }
        }
        agent.destroy(SixDirection.Up)
        agent.move(SixDirection.Up, 1)
        agent.turn(TurnDirection.Left)
        agent.turn(TurnDirection.Left)
    }
})
player.onChat("go", function (WhereTo) {
    if (WhereTo == 1) {
        gameplay.setGameMode(
        GameMode.Survival,
        mobs.target(TargetSelectorKind.LocalPlayer)
        )
        player.teleport(positions.createWorld(player.position().getValue(Axis.X), 12, player.position().getValue(Axis.Z)))
    } else if (WhereTo == 2) {
        gameplay.setGameMode(
        GameMode.Creative,
        mobs.target(TargetSelectorKind.LocalPlayer)
        )
        player.teleport(positions.createWorld(player.position().getValue(Axis.X), 100, player.position().getValue(Axis.Z)))
    } else {
        player.say("Enter 1 to go down or 2 to go up")
        player.say("Example >> \"go 1\"")
    }
})
```

### Challenge 2 - Add More Conditions

```blocks
player.onChat("do", function (AgentOrder) {
    if (AgentOrder == 1) {
        agent.teleportToPlayer()
    } else if (AgentOrder == 2) {
        agent.turn(TurnDirection.Left)
    } else {
        player.say("Enter 1 to teleport or 2 to turn")
    }
})
player.onChat("dig", function () {
    for (let i = 0; i < 2; i++) {
        for (let i = 0; i < 64; i++) {
            if (agent.inspect(AgentInspection.Block, SixDirection.Forward) == blocks.block(Block.DiamondOre)) {
                player.say("We’re rich!")
                agent.destroy(SixDirection.Forward)
                agent.move(SixDirection.Forward, 1)
                agent.collectAll()
            } else {
                agent.destroy(SixDirection.Forward)
                agent.move(SixDirection.Forward, 1)
            }
        }
        agent.destroy(SixDirection.Up)
        agent.move(SixDirection.Up, 1)
        agent.turn(TurnDirection.Left)
        agent.turn(TurnDirection.Left)
    }
})
player.onChat("go", function (WhereTo) {
    if (WhereTo == 1) {
        mobs.give(
        mobs.target(TargetSelectorKind.LocalPlayer),
        blocks.block(Block.Torch),
        64
        )
        gameplay.setGameMode(
        GameMode.Survival,
        mobs.target(TargetSelectorKind.LocalPlayer)
        )
        player.teleport(positions.createWorld(player.position().getValue(Axis.X), 12, player.position().getValue(Axis.Z)))
        blocks.fill(
        blocks.block(Block.Air),
        positions.create(5, 0, 5),
        positions.create(-5, 3, -5),
        FillOperation.Replace
        )
        agent.teleportToPlayer()
    } else if (WhereTo == 2) {
        gameplay.setGameMode(
        GameMode.Creative,
        mobs.target(TargetSelectorKind.LocalPlayer)
        )
        player.teleport(positions.createWorld(player.position().getValue(Axis.X), 100, player.position().getValue(Axis.Z)))
    } else {
        player.say("Enter 1 to go down or 2 to go up")
        player.say("Example >> \"go 1\"")
    }
})
```

## Experiments

## Experiment 1 - Standard Checkerboard

```blocks
player.onChat("checkers", function () {
    agent.teleportToPlayer()
    agent.move(SixDirection.Forward, 1)
    for (let i = 0; i < 10; i++) {
        for (let j = 0; j < 5; j++) {
            agent.move(SixDirection.Forward, 1)
            agent.setSlot(1)
            agent.place(SixDirection.Back)
            agent.move(SixDirection.Forward, 1)
            agent.setSlot(2)
            agent.place(SixDirection.Back)
        }
        if (i % 2 == 0)
            agent.turn(TurnDirection.Left)
        else
            agent.turn(TurnDirection.Right)
        agent.move(SixDirection.Forward, 1)
        if (i % 2 == 0)
            agent.turn(TurnDirection.Left)
        else
            agent.turn(TurnDirection.Right)
        agent.move(SixDirection.Forward, 1)
    }
})
```

## Experiment 2 - Maze Digger

```blocks
let RandomTurnNum = 0
player.onChat("digmaze", function () {
    agent.move(SixDirection.Forward, 5)
    for (let index = 0; index <= 10; index++) {
        if (index % 2 == 0) {
            tunnel()
        } else {
            TurnRandom()
            tunnel()
        }
    }
})
player.onChat("go", function (WhereTo) {
    if (WhereTo == 1) {
        mobs.give(
        mobs.target(TargetSelectorKind.LocalPlayer),
        blocks.block(Block.Torch),
        64
        )
        gameplay.setGameMode(
        GameMode.Survival,
        mobs.target(TargetSelectorKind.LocalPlayer)
        )
        player.teleport(positions.createWorld(player.position().getValue(Axis.X), 12, player.position().getValue(Axis.Z)))
        blocks.fill(
        blocks.block(Block.Air),
        positions.create(5, 0, 5),
        positions.create(-5, 3, -5),
        FillOperation.Replace
        )
        agent.teleportToPlayer()
    } else if (WhereTo == 2) {
        gameplay.setGameMode(
        GameMode.Creative,
        mobs.target(TargetSelectorKind.LocalPlayer)
        )
        player.teleport(positions.createWorld(player.position().getValue(Axis.X), 100, player.position().getValue(Axis.Z)))
    } else {
        player.say("Enter 1 to go down or 2 to go up")
        player.say("Example >> \"go 1\"")
    }
})
function tunnel() {
    for (let i = 0; i < 5; i++) {
        agent.destroy(SixDirection.Forward)
        agent.destroy(SixDirection.Up)
        agent.move(SixDirection.Forward, 1)
    }
}
function TurnRandom() {
    RandomTurnNum = Math.randomRange(0, 1)
    if (RandomTurnNum == 0) {
        agent.turn(TurnDirection.Left)
    } else {
        agent.turn(TurnDirection.Right)
    }
}
```