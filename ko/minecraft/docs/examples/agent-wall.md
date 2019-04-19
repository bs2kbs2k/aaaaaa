# 에이전트 벽 만들기

![The agent makes a tall wall](/static/mods/agent-wall.jpg)

Move the agent back and forth to build a wall.

## Try the code:

```blocks
player.onChat("wall", function () {
    agent.teleportToPlayer()
    agent.setAssist(AgentAssist.PlaceOnMove, true)
    agent.setAssist(AgentAssist.DetroyObstacles, true)
    for (let i = 0; i < 10; i++) {
        agent.move(SixDirection.Forward, 4)
        agent.move(SixDirection.Up, 1)
        agent.turn(TurnDirection.Left)
        agent.turn(TurnDirection.Left)
    }
})
```