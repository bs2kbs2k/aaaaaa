# Activity: Maze Generation

## Challenge

### Challenge 1 - Give the Player a Perch for the Bird's-Eye View

```blocks
let dirs: number[] = []
let index2 = 0
let index = 0
let right = 0
let left = 0
let forward = 0
let temp = 0
let moves: string[] = []
let tempArray: number[] = []
player.onChat("maze", function () {
    blocks.fill(
    blocks.block(Block.Stone),
    positions.create(-5, 0, -5),
    positions.create(5, 0, 5),
    FillOperation.Replace
    )
    agent.teleportToPlayer()
    blocks.place(blocks.block(Block.Air), positions.create(0, 0, 0))
    agent.setAssist(AgentAssist.DetroyObstacles, false)
    blocks.place(blocks.block(Block.Bookshelf), positions.create(0, 5, 0))
    player.teleport(positions.create(0, 7, 0))
    player.say("let's dig that maze!")
    dig()
})
function shuffle() {
    tempArray = [forward, left, right]
    for (let i = 0; i < 3; i++) {
        index = Math.randomRange(0, 2)
        index2 = Math.randomRange(0, 2)
        temp = tempArray[index]
        tempArray[index] = tempArray[index2]
        tempArray[index2] = temp
    }
    for (let k = 0; k <= 3 - 1; k++) {
        dirs.push(tempArray[k])
    }
}
function dig() {
    player.say("dig deeper")
    shuffle()
    for (let i = 0; i < 3; i++) {
        player.say("try " + moves[dirs[dirs.length - 1]])
        // turn towards the new direction
        if (dirs[dirs.length - 1] == left) {
            agent.turn(TurnDirection.Left)
        } else if (dirs[dirs.length - 1] == right) {
            agent.turn(TurnDirection.Right)
        }
        // is this a wall?
        if (agent.detect(AgentDetection.Block, SixDirection.Forward)) {
            // dig once
            agent.destroy(SixDirection.Forward)
            agent.move(SixDirection.Forward, 1)
            // did we dig through a wall?
            if (!(agent.detect(AgentDetection.Block, SixDirection.Forward))) {
                player.say("oops, that was a wall")
                // move back and put the wall back
                agent.move(SixDirection.Back, 1)
                agent.place(SixDirection.Forward)
            } else {
                // yay! keep digging
                agent.destroy(SixDirection.Forward)
                agent.move(SixDirection.Forward, 1)
                // did we reach the end of the maze?
                if (!(agent.detect(AgentDetection.Block, SixDirection.Forward))) {
                    // go back and place wall
                    player.say("oops, too far")
                    agent.move(SixDirection.Back, 1)
                    agent.place(SixDirection.Forward)
                    agent.move(SixDirection.Back, 1)
                } else {
                    dig()
                    // start roll back
                    agent.move(SixDirection.Back, 2)
                }
            }
        }
        // turn back to the original direction
        if (dirs[dirs.length - 1] == left) {
            agent.turn(TurnDirection.Right)
        } else if (dirs[dirs.length - 1] == right) {
            agent.turn(TurnDirection.Left)
        }
        temp = dirs.pop()
    }
}
moves = ["forward", "left", "right"]
temp = 1
forward = 0
left = 1
right = 2
```

### Challenge 2 - Redecorate the Maze

```blocks
let dirs: number[] = []
let index2 = 0
let index = 0
let right = 0
let left = 0
let forward = 0
let temp = 0
let moves: string[] = []
let tempArray: number[] = []
player.onChat("maze", function () {
    blocks.fill(
    blocks.block(Block.EmeraldBlock),
    positions.create(-5, 0, -5),
    positions.create(5, 0, 5),
    FillOperation.Replace
    )
    blocks.fill(
    blocks.block(Block.MagentaGlazedTerracotta),
    positions.create(-5, -1, -5),
    positions.create(5, -1, 5),
    FillOperation.Replace
    )
    agent.teleportToPlayer()
    blocks.place(blocks.block(Block.Air), positions.create(0, 0, 0))
    agent.setAssist(AgentAssist.DetroyObstacles, false)
    blocks.place(blocks.block(Block.Bookshelf), positions.create(0, 5, 0))
    player.teleport(positions.create(0, 7, 0))
    player.say("let's dig that maze!")
    dig()
})
function shuffle() {
    tempArray = [forward, left, right]
    for (let i = 0; i < 3; i++) {
        index = Math.randomRange(0, 2)
        index2 = Math.randomRange(0, 2)
        temp = tempArray[index]
        tempArray[index] = tempArray[index2]
        tempArray[index2] = temp
    }
    for (let k = 0; k <= 3 - 1; k++) {
        dirs.push(tempArray[k])
    }
}
function dig() {
    player.say("dig deeper")
    shuffle()
    for (let i = 0; i < 3; i++) {
        player.say("try " + moves[dirs[dirs.length - 1]])
        // turn towards the new direction
        if (dirs[dirs.length - 1] == left) {
            agent.turn(TurnDirection.Left)
        } else if (dirs[dirs.length - 1] == right) {
            agent.turn(TurnDirection.Right)
        }
        // is this a wall?
        if (agent.detect(AgentDetection.Block, SixDirection.Forward)) {
            // dig once
            agent.destroy(SixDirection.Forward)
            agent.move(SixDirection.Forward, 1)
            // did we dig through a wall?
            if (!(agent.detect(AgentDetection.Block, SixDirection.Forward))) {
                player.say("oops, that was a wall")
                // move back and put the wall back
                agent.move(SixDirection.Back, 1)
                agent.place(SixDirection.Forward)
            } else {
                // yay! keep digging
                agent.destroy(SixDirection.Forward)
                agent.move(SixDirection.Forward, 1)
                // did we reach the end of the maze?
                if (!(agent.detect(AgentDetection.Block, SixDirection.Forward))) {
                    // go back and place wall
                    player.say("oops, too far")
                    agent.move(SixDirection.Back, 1)
                    agent.place(SixDirection.Forward)
                    agent.move(SixDirection.Back, 1)
                } else {
                    dig()
                    // start roll back
                    agent.move(SixDirection.Back, 2)
                }
            }
        }
        // turn back to the original direction
        if (dirs[dirs.length - 1] == left) {
            agent.turn(TurnDirection.Right)
        } else if (dirs[dirs.length - 1] == right) {
            agent.turn(TurnDirection.Left)
        }
        temp = dirs.pop()
    }
}
moves = ["forward", "left", "right"]
temp = 1
forward = 0
left = 1
right = 2
```