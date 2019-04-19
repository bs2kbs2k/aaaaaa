# Agent Fractals

![Maze-shaped fractal](/static/mods/hilbert-fractals.jpg)

A fun maze-like fractal built with the agent. This maze is built as a [Hilburt curve](https://wikipedia.org/wiki/Hilbert_curve) fractal.

## Try the code:

```typescript
function turn(direction: TurnDirection, a: number) {
    if (a < 0) {
        direction = direction == TurnDirection.Left ? TurnDirection.Right: TurnDirection.Left;
    }
    agent.turn(direction)
}

function hilbert(n: number, a: number, h: number) {
    if (n <= 0) {
        return;
    }
    turn(TurnDirection.Right, a)
    hilbert(n - 1, -a, h);
    agent.move(SixDirection.Forward, h);
    turn(TurnDirection.Left, a);
    hilbert(n - 1, a, h);
    agent.move(SixDirection.Forward, h);
    hilbert(n - 1, a, h);
    turn(TurnDirection.Left, a);
    agent.move(SixDirection.Forward, h);
    hilbert(n - 1, -a, h);
    turn(TurnDirection.Right, a);
}

player.onChat("hilbert", function () {
    agent.setAssist(AgentAssist.PlaceOnMove, true)
    agent.teleportToPlayer()
    hilbert(5, 1, 2)
})
```