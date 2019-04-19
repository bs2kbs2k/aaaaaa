# Activity: Tree Hunter

## Challenges

### Challenge 1 - Create Comments to Show You Understand What Each Part of the Code Does

```blocks
let flipturn = false
let height = 0
// Agent inspects blocks to the left, forward, and
// right to see if there is a tree.
function search() {
    if (agent.inspect(AgentInspection.Block, SixDirection.Left) == blocks.block(Block.LogOak)) {
        agent.turn(TurnDirection.Left)
        chop()
        agent.turn(TurnDirection.Right)
    } else if (agent.inspect(AgentInspection.Block, SixDirection.Forward) == blocks.block(Block.LogOak)) {
        chop()
    } else if (agent.inspect(AgentInspection.Block, SixDirection.Right) == blocks.block(Block.LogOak)) {
        agent.turn(TurnDirection.Right)
        chop()
        agent.turn(TurnDirection.Left)
    } else {

    }
}
// Agent turns at the end of a row.  This alternates
// between left and right.
function turn() {
    agent.setAssist(AgentAssist.DetroyObstacles, true)
    if (flipturn) {
        agent.turn(TurnDirection.Right)
        agent.move(SixDirection.Forward, 3)
        agent.turn(TurnDirection.Right)
    } else {
        agent.turn(TurnDirection.Left)
        agent.move(SixDirection.Forward, 3)
        agent.turn(TurnDirection.Left)
    }
    flipturn = !(flipturn)
}
// Agent moves up one block if the elevation goes up. 
// Agent goes down one block if the elevation goes
// down.
function follow() {
    agent.move(SixDirection.Forward, 1)
    if (agent.inspect(AgentInspection.Block, SixDirection.Forward) == blocks.block(Block.Grass)) {
        agent.destroy(SixDirection.Up)
        agent.move(SixDirection.Up, 1)
    } else if (!(agent.detect(AgentDetection.Block, SixDirection.Down))) {
        agent.move(SixDirection.Down, 1)
    } else {

    }
}
player.onChat("runchopper", function (area) {
    // Agent destroys obstacles in its way.
    agent.setAssist(AgentAssist.DetroyObstacles, true)
    flipturn = false
    // Agent repeats search to complete a square search
    // area based on user input.
    for (let i = 0; i < area / 3; i++) {
        // Agent searches 3 rows of the grid
        for (let i = 0; i < area; i++) {
            search()
            follow()
        }
        turn()
    }
})
// Agent chops a tree.
function chop() {
    height = 0
    while (agent.detect(AgentDetection.Block, SixDirection.Forward)) {
        height += 1
        agent.destroy(SixDirection.Up)
        agent.move(SixDirection.Up, 1)
    }
    for (let i = 0; i < height; i++) {
        agent.move(SixDirection.Down, 1)
        agent.destroy(SixDirection.Forward)
    }
    agent.collectAll()
}
player.onChat("tp", function () {
    agent.teleportToPlayer()
})
player.onChat("lt", function () {
    agent.turn(TurnDirection.Left)
})
```

### Challenge 2 - Agent Gives Feedback

```blocks
let height = 0
let flipturn = false
player.onChat("runchopper", function (area) {
    agent.setAssist(AgentAssist.DetroyObstacles, true)
    flipturn = false
    for (let i = 0; i < area / 3; i++) {
        for (let i = 0; i < area; i++) {
            search()
            follow()
        }
        turn()
    }
})
function search() {
    if (agent.inspect(AgentInspection.Block, SixDirection.Left) == blocks.block(Block.LogOak)) {
        player.say("Tree found on the left")
        agent.turn(TurnDirection.Left)
        chop()
        agent.turn(TurnDirection.Right)
    } else if (agent.inspect(AgentInspection.Block, SixDirection.Forward) == blocks.block(Block.LogOak)) {
        player.say("Tree found in front of me")
        chop()
    } else if (agent.inspect(AgentInspection.Block, SixDirection.Right) == blocks.block(Block.LogOak)) {
        player.say("Tree found to my right")
        agent.turn(TurnDirection.Right)
        chop()
        agent.turn(TurnDirection.Left)
    } else {

    }
}
function follow() {
    agent.move(SixDirection.Forward, 1)
    if (agent.inspect(AgentInspection.Block, SixDirection.Forward) == blocks.block(Block.Grass)) {
        player.say("Need to Move Up")
        agent.destroy(SixDirection.Up)
        agent.move(SixDirection.Up, 1)
    } else if (!(agent.detect(AgentDetection.Block, SixDirection.Down))) {
        player.say("Moving Down to the Ground")
        agent.move(SixDirection.Down, 1)
    } else {

    }
}
function turn() {
    agent.setAssist(AgentAssist.DetroyObstacles, true)
    if (flipturn) {
        player.say("Finished a row and turning right!")
        agent.turn(TurnDirection.Right)
        agent.move(SixDirection.Forward, 3)
        agent.turn(TurnDirection.Right)
    } else {
        player.say("Finished a row and turning left!")
        agent.turn(TurnDirection.Left)
        agent.move(SixDirection.Forward, 3)
        agent.turn(TurnDirection.Left)
    }
    flipturn = !(flipturn)
}
player.onChat("tp", function () {
    agent.teleportToPlayer()
})
function chop() {
    player.say("Chopping Tree....")
    height = 0
    while (agent.detect(AgentDetection.Block, SixDirection.Forward)) {
        height += 1
        agent.destroy(SixDirection.Up)
        agent.move(SixDirection.Up, 1)
    }
    for (let i = 0; i < height; i++) {
        agent.move(SixDirection.Down, 1)
        agent.destroy(SixDirection.Forward)
    }
    agent.collectAll()
}
player.onChat("lt", function () {
    agent.turn(TurnDirection.Left)
})
```