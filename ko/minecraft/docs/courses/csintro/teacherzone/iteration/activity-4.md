# Activity: One Block At a Time

## Challenges

### Challenge 1 - Turn One Line into a Square

```blocks
player.onChat("square", function () {
    for (let i = 0; i < 4; i++) {
        for (let i = 0; i < 6; i++) {
            agent.destroy(SixDirection.Down)
            agent.place(SixDirection.Down)
            agent.move(SixDirection.Forward, 1)
        }
        agent.turn(TurnDirection.Right)
    }
})
player.onChat("tp", function () {
    agent.teleportToPlayer()
})
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
```

### Challenge 2 - Make a Tower

```blocks
player.onChat("square", function () {
    for (let i = 0; i < 20; i++) {
        for (let i = 0; i < 4; i++) {
            for (let i = 0; i < 6; i++) {
                agent.destroy(SixDirection.Down)
                agent.place(SixDirection.Down)
                agent.move(SixDirection.Forward, 1)
            }
            agent.turn(TurnDirection.Right)
        }
        agent.move(SixDirection.Up, 1)
    }
})
player.onChat("tp", function () {
    agent.teleportToPlayer()
})
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
```

## Experiments

### Experiment 1 - Starter Castle

```blocks
player.onChat("castle", function () {
    for (let i = 0; i < 2; i++) {
        for (let i = 0; i < 10; i++) {
            for (let i = 0; i < 4; i++) {
                for (let i = 0; i < 6; i++) {
                    agent.destroy(SixDirection.Down)
                    agent.place(SixDirection.Down)
                    agent.move(SixDirection.Forward, 1)
                }
                agent.turn(TurnDirection.Right)
            }
            agent.move(SixDirection.Up, 1)
        }
        agent.move(SixDirection.Forward, 17)
        agent.move(SixDirection.Down, 20)
    }
})
player.onChat("tp", function () {
    agent.teleportToPlayer()
})
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
```