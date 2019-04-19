# Activity: Maze Pathfinding

## Challenges

### Challenge 1 - Fool the AI

### Challenge 2 - Agent Feedback

```blocks
player.onChat("mr", function () {
    while (!(agent.detect(AgentDetection.Redstone, SixDirection.Down))) {
        if (!(agent.detect(AgentDetection.Block, SixDirection.Left))) {
            agent.turn(TurnDirection.Left)
            agent.move(SixDirection.Forward, 1)
            player.say("Oh! Better turn left, I hit a wall!")
        } else if (!(agent.detect(AgentDetection.Block, SixDirection.Forward))) {
            agent.move(SixDirection.Forward, 1)
            player.say("I guess I will just keep moving forward!")
        } else if (!(agent.detect(AgentDetection.Block, SixDirection.Right))) {
            agent.turn(TurnDirection.Right)
            agent.move(SixDirection.Forward, 1)
            player.say("Right looks clear, I will go that way!")
        } else {
            agent.turn(TurnDirection.Left)
            agent.turn(TurnDirection.Left)
            agent.move(SixDirection.Forward, 1)
            player.say("Deadend!  I better turn around...")
        }
    }
    player.runChatCommand("dance")
})
player.onChat("dance", function () {
    for (let i = 0; i < 4; i++) {
        agent.move(SixDirection.Left, 1)
        agent.attack(SixDirection.Forward)
        agent.move(SixDirection.Right, 1)
        agent.move(SixDirection.Right, 1)
        agent.move(SixDirection.Left, 1)
    }
})
player.onChat("tp", function () {
    agent.teleportToPlayer()
})
player.onChat("lt", function () {
    agent.turn(TurnDirection.Left)
})
player.onChat("fd", function () {
    agent.move(SixDirection.Forward, 1)
})
player.onChat("rt", function () {
    agent.turn(TurnDirection.Right)
})
player.onChat("bk", function () {
    agent.move(SixDirection.Back, 1)
})

```

### Challenges 3 - Leave Trail of Breadcrumbs

```blocks
player.onChat("fd", function () {
    agent.move(SixDirection.Forward, 1)
})
player.onChat("lt", function () {
    agent.turn(TurnDirection.Left)
})
player.onChat("bk", function () {
    agent.move(SixDirection.Back, 1)
})
player.onChat("rt", function () {
    agent.turn(TurnDirection.Right)
})
player.onChat("mr", function () {
    while (!(agent.detect(AgentDetection.Redstone, SixDirection.Down))) {
        if (!(agent.detect(AgentDetection.Block, SixDirection.Left))) {
            agent.turn(TurnDirection.Left)
            agent.till(SixDirection.Forward)
            agent.move(SixDirection.Forward, 1)
        } else if (!(agent.detect(AgentDetection.Block, SixDirection.Forward))) {
            agent.till(SixDirection.Forward)
            agent.move(SixDirection.Forward, 1)
        } else if (!(agent.detect(AgentDetection.Block, SixDirection.Right))) {
            agent.turn(TurnDirection.Right)
            agent.till(SixDirection.Forward)
            agent.move(SixDirection.Forward, 1)
        } else {
            agent.turn(TurnDirection.Left)
            agent.turn(TurnDirection.Left)
            agent.till(SixDirection.Forward)
            agent.move(SixDirection.Forward, 1)
        }
    }
    player.runChatCommand("dance")
})
player.onChat("tp", function () {
    agent.teleportToPlayer()
})
player.onChat("dance", function () {
    for (let i = 0; i < 4; i++) {
        agent.move(SixDirection.Left, 1)
        agent.attack(SixDirection.Forward)
        agent.move(SixDirection.Right, 1)
        agent.move(SixDirection.Right, 1)
        agent.move(SixDirection.Left, 1)
    }
})
```