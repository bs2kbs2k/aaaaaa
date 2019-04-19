# Agent Checkers

Have your agent build a checker board. Make sure slot 1 and 2 have blocks!

![A checker board of blocks](/static/mods/agent-checkers.jpg)

## Try the code:

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