# Activity: Agent Tree Chopper

## Challenges

### Challenge 1 - Teleport Agent and Get Some Things Set Up for Challenge 2

```blocks
let height = 0
let TurnToTree = false
player.onChat("chop", function () {
    agent.teleportToPlayer()
    TurnToTree = true
    height = 0
    while (TurnToTree) {
        agent.turn(TurnDirection.Left)
    }
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
})
```

### Challenge 2 - Have the Agent Face the Tree Automatically

```blocks
let height = 0
let TurnToTree = false
player.onChat("chop", function () {
    agent.teleportToPlayer()
    TurnToTree = true
    height = 0
    while (TurnToTree) {
        agent.turn(TurnDirection.Left)
        if (agent.detect(AgentDetection.Block, SixDirection.Forward)) {
            TurnToTree = false
        }
    }
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
})
```

## Experiments

## Experiment 1 - Increase the Size of the Hole

```blocks
player.onChat("dig", function (levels) {
    if (levels > 0) {
        agent.teleportToPlayer()
        for (let i = 0; i < levels; i++) {
            for (let i = 0; i < 4; i++) {
                agent.move(SixDirection.Forward, 1)
                if (agent.detect(AgentDetection.Block, SixDirection.Down)) {
                    agent.destroy(SixDirection.Down)
                    agent.collectAll()
                }
                agent.turn(TurnDirection.Left)
            }
            agent.move(SixDirection.Down, 1)
        }
    } else {
        player.say("  ")
        player.say("%%%%%%%  Information  %%%%%%%")
        player.say("Enter the number of levels you want the agent to dig.")
        player.say("Example >> \"dig 5\"")
        player.say("  ")
        player.say("%%%%%%%%%%%%%%%%%%%%%%%%%%%%")
    }
})
```

![Agent - Dig 4](/static/courses/csintro/conditionals/dig1.jpg)

## Experiment 2 - Create a Maze

```blocks
let MoveForward = false
player.onChat("dig", function (levels, HowFarForward) {
    if (levels > 0) {
        agent.teleportToPlayer()
        MoveForward = true
        for (let i = 0; i < levels; i++) {
            for (let i = 0; i < 4; i++) {
                agent.move(SixDirection.Forward, 1)
                if (agent.detect(AgentDetection.Block, SixDirection.Down)) {
                    agent.destroy(SixDirection.Down)
                    agent.collectAll()
                }
                agent.turn(TurnDirection.Left)
            }
            agent.move(SixDirection.Down, 1)
        }
        while (MoveForward) {
            agent.move(SixDirection.Forward, 1)
            if (agent.detect(AgentDetection.Block, SixDirection.Forward)) {
                MoveForward = false
            }
        }
        for (let i = 0; i < HowFarForward; i++) {
            agent.destroy(SixDirection.Forward)
            agent.move(SixDirection.Forward, 1)
            agent.destroy(SixDirection.Up)
            agent.destroy(SixDirection.Left)
            agent.destroy(SixDirection.Right)
        }
        agent.turn(TurnDirection.Left)
        agent.turn(TurnDirection.Left)
        agent.destroy(SixDirection.Down)
        agent.move(SixDirection.Down, 1)
        for (let i = 0; i < HowFarForward; i++) {
            agent.destroy(SixDirection.Forward)
            agent.move(SixDirection.Forward, 1)
            agent.destroy(SixDirection.Up)
            agent.destroy(SixDirection.Left)
            agent.destroy(SixDirection.Right)
        }
    } else {
        player.say("  ")
        player.say("%%%%%%%  Information  %%%%%%%")
        player.say("Enter the number of levels you want the agent to dig.")
        player.say("Example >> \"dig 5\"")
        player.say("  ")
        player.say("%%%%%%%%%%%%%%%%%%%%%%%%%%%%")
    }
})
```