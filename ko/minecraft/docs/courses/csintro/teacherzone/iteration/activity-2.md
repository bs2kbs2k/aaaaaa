# Activity: Dance Dance Agent

## Challenges

### Challenge 1 - A Second Repeat Loop

```blocks
player.onChat("dance", function () {
    for (let i = 0; i < 4; i++) {
        agent.move(SixDirection.Left, 1)
        agent.attack(SixDirection.Forward)
        for (let i = 0; i < 3; i++) {
            agent.move(SixDirection.Right, 1)
        }
        agent.turn(TurnDirection.Left)
        agent.move(SixDirection.Left, 1)
    }
})
player.onChat("tp", function () {
    agent.teleportToPlayer()
})
```

### Challenge 2 - Adding a 3, 2, 1 Start

```blocks
let countdown = 0
player.onChat("tp", function () {
    agent.teleportToPlayer()
})
player.onChat("dance", function () {
    countdown = 3
    for (let index = 0; index <= 2; index++) {
        player.say(" " + countdown)
        countdown += -1
    }
    for (let i = 0; i < 4; i++) {
        agent.move(SixDirection.Left, 1)
        agent.attack(SixDirection.Forward)
        agent.move(SixDirection.Right, 1)
        agent.move(SixDirection.Right, 1)
        agent.move(SixDirection.Right, 1)
        agent.turn(TurnDirection.Left)
        agent.move(SixDirection.Left, 1)
    }
})
```

## Experiments

### Experiment 1 - You Dance When I Say

```blocks
let KeepDancing = false
player.onChat("tp", function () {
    agent.teleportToPlayer()
})
player.onChat("dance", function () {
    KeepDancing = true
})
player.onChat("stop", function () {
    KeepDancing = false
})
loops.forever(function () {
    while (KeepDancing) {
        agent.move(SixDirection.Left, 1)
        agent.attack(SixDirection.Forward)
        for (let i = 0; i < 3; i++) {
            agent.move(SixDirection.Right, 1)
        }
        agent.turn(TurnDirection.Left)
        agent.move(SixDirection.Left, 1)
    }
})
```

### Experiment 2 - Instant Dance Floor

```blocks
let countdown = 0
let DanceFloorBlock = 0
player.onChat("dance", function () {
    player.teleport(positions.create(4, 0, 4))
    agent.teleportToPlayer()
    player.teleport(positions.create(-4, 0, -4))
    countdown = 3
    for (let index = 0; index <= 2; index++) {
        player.say(" " + countdown)
        countdown += -1
    }
    MakeDanceFloor()
    for (let i = 0; i < 10; i++) {
        agent.move(SixDirection.Left, 1)
        agent.attack(SixDirection.Forward)
        agent.move(SixDirection.Right, 1)
        agent.move(SixDirection.Right, 1)
        agent.move(SixDirection.Right, 1)
        agent.turn(TurnDirection.Left)
        agent.move(SixDirection.Left, 1)
    }
})
function GetRandomBlockForFloor() {
    DanceFloorBlock = Math.randomRange(0, 7)
    if (DanceFloorBlock == 0) {
        DanceFloorBlock = blocks.block(Block.LapisOre)
    } else if (DanceFloorBlock == 1) {
        DanceFloorBlock = blocks.block(Block.Glass)
    } else if (DanceFloorBlock == 2) {
        DanceFloorBlock = blocks.block(Block.RedstoneBlock)
    } else if (DanceFloorBlock == 3) {
        DanceFloorBlock = blocks.block(Block.Glowstone)
    } else if (DanceFloorBlock == 4) {
        DanceFloorBlock = blocks.block(Block.RedMushroomBlock)
    } else if (DanceFloorBlock == 5) {
        DanceFloorBlock = blocks.block(Block.EmeraldBlock)
    } else if (DanceFloorBlock == 6) {
        DanceFloorBlock = blocks.block(Block.MagentaGlazedTerracotta)
    } else {
        DanceFloorBlock = blocks.block(Block.LimeGlazedTerracotta)
    }
}
function MakeDanceFloor() {
    for (let row = 0; row <= 8; row++) {
        for (let column = 0; column <= 8; column++) {
            GetRandomBlockForFloor()
            blocks.place(DanceFloorBlock, positions.create(row, -1, column))
        }
    }
}
```