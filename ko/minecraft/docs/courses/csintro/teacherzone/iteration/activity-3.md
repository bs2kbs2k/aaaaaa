# Activity: Help Your Agent Farm

## Challenges

### Challenge 1 - Get Agent to Till Aligned Rows

```blocks
player.onChat("farm", function () {
    for (let i = 0; i < 2; i++) {
        for (let i = 0; i < 5; i++) {
            agent.till(SixDirection.Forward)
            agent.move(SixDirection.Forward, 1)
        }
        agent.turn(TurnDirection.Left)
        agent.till(SixDirection.Forward)
        agent.move(SixDirection.Forward, 1)
        agent.turn(TurnDirection.Left)
    }
})
player.onChat("tp", function () {
    agent.teleportToPlayer()
})
player.onChat("turn", function () {
    agent.turn(TurnDirection.Right)
})
player.onChat("turn180", function () {
    for (let i = 0; i < 2; i++) {
        agent.turn(TurnDirection.Right)
    }
})
```

### Challenge 2 - Get Agent to Till a 5x6 Plot of Aligned Soil

```blocks
player.onChat("farm", function () {
    for (let i = 0; i < 3; i++) {
        for (let i = 0; i < 2; i++) {
            for (let i = 0; i < 4; i++) {
                agent.till(SixDirection.Forward)
                agent.move(SixDirection.Forward, 1)
            }
            agent.turn(TurnDirection.Left)
            agent.till(SixDirection.Forward)
            agent.move(SixDirection.Forward, 1)
            agent.turn(TurnDirection.Left)
        }
        agent.turn(TurnDirection.Right)
        agent.move(SixDirection.Forward, 2)
        agent.turn(TurnDirection.Left)
    }
})
player.onChat("turn", function () {
    agent.turn(TurnDirection.Right)
})
player.onChat("tp", function () {
    agent.teleportToPlayer()
})
player.onChat("turn180", function () {
    for (let i = 0; i < 2; i++) {
        agent.turn(TurnDirection.Right)
    }
})
```

## Experiments

### Experiment 1 - Creating a Help Menu for Users

```blocks
let AgentOrder = 0
function OrderAgent() {
    if (AgentOrder == 1) {
        agent.move(SixDirection.Forward, 1)
    } else if (AgentOrder == 2) {
        agent.move(SixDirection.Back, 1)
    } else if (AgentOrder == 3) {
        agent.turn(TurnDirection.Left)
    } else if (AgentOrder == 4) {
        agent.turn(TurnDirection.Right)
    } else if (AgentOrder == 5) {
        for (let i = 0; i < 2; i++) {
            agent.turn(TurnDirection.Right)
        }
    } else if (AgentOrder == 6) {
        agent.teleportToPlayer()
    } else {
        ListAgentOrder()
    }
}
player.onChat("do", function (GetAgentOrderFromUser) {
    AgentOrder = GetAgentOrderFromUser
    OrderAgent()
})
player.onChat("?", function () {
    ListAgentOrder()
})
function ListAgentOrder() {
    player.say("Enter 'Do' followed by a space and one of these numbers")
    player.say("Example - 'Do 0' moves you forward 1")
    player.say("1 = forward")
    player.say("2 = back")
    player.say("3 = turn left")
    player.say("4 = turn right")
    player.say("5 = turn 180")
    player.say("6 = teleport agent")
}
```

### Experiment 2 - Creating a Raised Farming Bed with Planted Crops

```blocks
let StartPosition: Position = null
let TaskNum = 0
function PerformTask() {
    if (TaskNum == 1) {
        agent.move(SixDirection.Forward, 1)
    } else if (TaskNum == 2) {
        agent.move(SixDirection.Back, 1)
    } else if (TaskNum == 3) {
        agent.turn(TurnDirection.Left)
    } else if (TaskNum == 4) {
        agent.turn(TurnDirection.Right)
    } else if (TaskNum == 5) {
        for (let i = 0; i < 2; i++) {
            agent.turn(TurnDirection.Right)
        }
    } else if (TaskNum == 6) {
        agent.teleportToPlayer()
    } else if (TaskNum == 7) {
        mobs.give(
        mobs.target(TargetSelectorKind.LocalPlayer),
        blocks.item(Item.Seeds),
        64
        )
    } else if (TaskNum == 8) {
        BuildRaisedFarmBed()
    } else if (TaskNum == 9) {
        plant()
    } else {
        Menu()
    }
}
player.onChat("do", function (GetTaskFromUser) {
    TaskNum = GetTaskFromUser
    PerformTask()
})
player.onChat("?", function () {
    Menu()
})
function Menu() {
    player.say(" ")
    player.say(" ")
    player.say("Just 'do' = Menu Options")
    player.say(" ")
    player.say("Enter 'Do' followed by a space and one of these numbers")
    player.say("Example - 'Do 0' moves you forward 1")
    player.say(" ")
    player.say("1 = forward  (agent)")
    player.say("2 = back  (agent)")
    player.say("3 = turn left  (agent)")
    player.say("4 = turn right  (agent)")
    player.say("5 = turn 180  (agent)")
    player.say("6 = teleport  (agent)")
    player.say("7 = give seeds to Character")
    player.say("8 = build raised farming bed")
    player.say("9 = plant seeds")
}
function BuildRaisedFarmBed() {
    StartPosition = positions.add(
    player.position(),
    positions.create(-1, 0, -1)
    )
    builder.teleportTo(StartPosition)
    builder.setOrigin()
    builder.mark()
    builder.shift(6, 0, 8)
    builder.fill(blocks.block(Block.LogOak))
    builder.teleportToOrigin()
    builder.shift(1, 0, 1)
    builder.mark()
    builder.shift(4, 0, 6)
    builder.fill(blocks.block(Block.Dirt))
    builder.teleportToOrigin()
    builder.shift(3, 0, 1)
    builder.mark()
    builder.move(SixDirection.Left, 6)
    builder.fill(blocks.block(Block.Water))
    player.teleport(positions.add(
    player.position(),
    positions.create(-1, 1, -2)
    ))
    agent.teleportToPlayer()
    loops.pause(300)
    blocks.place(blocks.block(Block.PolishedAndesite), positions.add(
    player.position(),
    positions.create(-10, 4, 0)
    ))
    player.teleport(positions.add(
    player.position(),
    positions.create(-10, 5, 0)
    ))
}
function plant() {
    for (let i = 0; i < 2; i++) {
        for (let i = 0; i < 7; i++) {
            agent.till(SixDirection.Forward)
            agent.place(SixDirection.Forward)
            agent.move(SixDirection.Forward, 1)
        }
        agent.move(SixDirection.Forward, 1)
        agent.turn(TurnDirection.Right)
        agent.move(SixDirection.Forward, 1)
        agent.turn(TurnDirection.Right)
    }
}
```