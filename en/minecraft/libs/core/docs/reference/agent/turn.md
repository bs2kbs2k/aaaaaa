# turn

Turn the agent in a specific direction.

```sig
agent.turn(TurnDirection.Left);
```

## Parameters

* **direction**: the turn direction, like: TurnDirection.Left

## Example

Make your agent turn around by making it turn right twice.

```blocks
for (let i = 0; i < 2; i++) {
    agent.turn(TurnDirection.Right);
}
```

## See Also

[`||agent:move||`](/reference/agent/move)