# Agent Wanderer

![Random trail of blocks](/static/mods/agent-wanderer.jpg)

The Agent randomly walks around leaving a trail of blocks.

## Try the code:

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