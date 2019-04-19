# Agent Dig

![The agent digging](/static/mods/agent-dig.jpg)

The agent works hard for you!

## Try the code:

```blocks
player.onChat("come", function () {
    player.say("Hello Agent!")
    agent.teleportToPlayer()
})
player.onChat("dig", function (levels) {
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
})
```