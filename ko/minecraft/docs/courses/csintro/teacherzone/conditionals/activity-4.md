# Activity: Pyramid

## Challenges

### Challenge 1 - Tell the User When the Pyramid Is Built

```blocks
let MadePyramid = false
// Teleports the agent near you but a little away so
// you have time to get out of his way when he starts
// building
player.onChat("tp", function () {
    player.teleport(positions.create(3, 0, 3))
    agent.teleportToPlayer()
    player.teleport(positions.create(-3, 0, -3))
})
player.onChat("turn", function () {
    agent.turn(TurnDirection.Left)
})
player.onChat("pyramid", function (BaseSize) {
    // Detect if we should continue building pyramid
    if (BaseSize > 0) {
        agent.setAssist(AgentAssist.PlaceOnMove, true)
        // Builds one level of the pyramid
        for (let i = 0; i <= 3; i++) {
            agent.move(SixDirection.Forward, BaseSize - 1)
            agent.turn(TurnDirection.Left)
        }
        agent.move(SixDirection.Up, 1)
        agent.setAssist(AgentAssist.PlaceOnMove, false)
        agent.move(SixDirection.Forward, 1)
        MadePyramid = true
        player.runChatCommand("pyramid " + (BaseSize - 2))
    } else {
        // Checks to see if pyramid just got made or the user
        // made a mistake
        if (MadePyramid) {
            player.say("Pyramid Done!")
        } else {

        }
    }
})
```

![Pyramid Done Message](/static/courses/csintro/conditionals/pyramid-done.jpg)

### Challenge 2 - Say Something If the User Enters 0 or No Size Is Entered

```blocks
let MadePyramid = false
// Teleports the agent near you but a little away so
// you have time to get out of his way when he starts
// building
player.onChat("tp", function () {
    player.teleport(positions.create(3, 0, 3))
    agent.teleportToPlayer()
    player.teleport(positions.create(-3, 0, -3))
})
player.onChat("pyramid", function (BaseSize) {
    // Detect if we should continue building pyramid
    if (BaseSize > 0) {
        agent.setAssist(AgentAssist.PlaceOnMove, true)
        // Builds one level of the pyramid
        for (let i = 0; i <= 3; i++) {
            agent.move(SixDirection.Forward, BaseSize - 1)
            agent.turn(TurnDirection.Left)
        }
        agent.move(SixDirection.Up, 1)
        agent.setAssist(AgentAssist.PlaceOnMove, false)
        agent.move(SixDirection.Forward, 1)
        MadePyramid = true
        player.runChatCommand("pyramid " + (BaseSize - 2))
    } else {
        // Checks to see if pyramid just got made or the user
        // made a mistake
        if (MadePyramid) {
            player.say("Pyramid Done!")
            MadePyramid = false
        } else {
            player.say("To make a pyramid enter a size >> Example - \"pyramid 5\"")
        }
    }
})
player.onChat("turn", function () {
    agent.turn(TurnDirection.Left)
})
```

## Experiments

### Experiment 1 - Wander

```blocks
let item = 0
player.onChat("wander", function () {
    agent.teleportToPlayer()
    agent.setAssist(AgentAssist.PlaceOnMove, true)
    agent.setAssist(AgentAssist.DetroyObstacles, true)
    for (let i = 0; i < 100; i++) {
        item = Math.randomRange(0, 10)
        if (item <= 1) {
            agent.turn(TurnDirection.Left)
        } else if (item <= 3) {
            agent.turn(TurnDirection.Right)
        } else {
            agent.move(SixDirection.Forward, 1)
        }
    }
})
```

![Agent - Wander](/static/courses/csintro/conditionals/wander1.jpg)

### Experiment 2 - Build a Colorful Pyramid into the Side of a Hill

```blocks
let ActiveInventorySlot = 0
player.onChat("pyramid", function (size) {
    if (size > 0) {
        agent.setAssist(AgentAssist.PlaceOnMove, true)
        if (ActiveInventorySlot < 1 || ActiveInventorySlot > 8) {
            // Change the active inventory slot variable to
            // remember it
            ActiveInventorySlot = 1
        } else {
            // Change the active inventory slot variable to
            // remember it
            ActiveInventorySlot = ActiveInventorySlot + 1
        }
        // Set the new inventory slot
        agent.setSlot(ActiveInventorySlot)
        // Tells how many walls to build
        for (let CurrWall = 0; CurrWall <= 3; CurrWall++) {
            // Builds walls block by block
            for (let Block_of_Current_Wall = 0; Block_of_Current_Wall <= size - 2; Block_of_Current_Wall++) {
                // As long as it is not the last block of the wall
                // destroy and move
                if (Block_of_Current_Wall < size - 2) {
                    agent.destroy(SixDirection.Forward)
                    agent.move(SixDirection.Forward, 1)
                } else {
                    // For the very last block of a level do nothing so
                    // our agent starts the next level in the right
                    // position
                    if (CurrWall < 3) {
                        agent.destroy(SixDirection.Forward)
                        agent.move(SixDirection.Forward, 1)
                    }
                }
            }
            agent.turn(TurnDirection.Left)
        }
        agent.move(SixDirection.Up, 1)
        agent.setAssist(AgentAssist.PlaceOnMove, false)
        agent.move(SixDirection.Forward, 1)
        // Call this same code again but this time the level
        // is smaller to give that pyramid look
        player.runChatCommand("pyramid " + (size - 2))
    }
})
player.onChat("do", function (Command) {
    if (Command == 0) {
        agent.teleportToPlayer()
    } else if (Command == 1) {
        agent.turn(TurnDirection.Left)
    } else {
        player.say("Please enter a command")
    }
})
```