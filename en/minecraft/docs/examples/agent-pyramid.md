# Agent Pyramid

![Pyramid of blocks](/static/mods/agent-pyramid.jpg)

A chat command that uses itself? The agent builds another layer of the pyramid every time the command runs itself. A good example of using *arguments*. Can you say *recursive*?

## Try the code:

```blocks
player.onChat("pyramid", function (size) {
    if (size > 0) {
        agent.setAssist(AgentAssist.PlaceOnMove, true)
        for (let i = 0; i <= 4 - 1; i++) {
            agent.move(SixDirection.Forward, size)
            agent.turn(TurnDirection.Left)
        }
        agent.move(SixDirection.Up, 1)
        agent.setAssist(AgentAssist.PlaceOnMove, false)
        agent.move(SixDirection.Forward, 1)
        player.runChatCommand("pyramid " + (size - 2))
    }
})
```