# 에이전트 타워 만들기

![Agent builds a tower](/static/mods/agent-tower.jpg)

The agent will build a tower, row by row.

## Try the code:

```blocks
player.onChat("tower", function () {
    agent.teleportToPlayer()
    agent.setAssist(AgentAssist.PlaceOnMove, true)
    agent.setAssist(AgentAssist.DetroyObstacles, true)
    for (let i = 0; i < 10; i++) {
        for (let i = 0; i < 4; i++) {
            agent.move(SixDirection.Forward, 4)
            agent.turn(TurnDirection.Left)
        }
        agent.move(SixDirection.Up, 1)
    }
})
```