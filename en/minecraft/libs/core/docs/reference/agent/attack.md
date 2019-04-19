# attack

Commands the agent to attack in the given direction.

```sig
agent.attack(SixDirection.Forward);
```

## Parameters

* **direction**: the direction in which to attack, eg: SixDirection.Forward

## Example

Makes the agent continuously attack around itself. Useful to defend against monsters!

```blocks
loops.forever(() => {
    agent.attack(SixDirection.Forward);
    agent.attack(SixDirection.Right);
    agent.attack(SixDirection.Back);
    agent.attack(SixDirection.Left);
    loops.pause(1000);
});
```