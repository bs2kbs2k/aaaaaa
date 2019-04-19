# drop All

Commands the agent to drop its entire inventory in the given direction.

```sig
agent.dropAll(SixDirection.Forward);
```

## Parameters

* **direction**: the direction in which to drop items, eg: SixDirection.Forward

## Example

Makes the agent drop everything it holds below itself.

```blocks
agent.dropAll(SixDirection.Down);
```

## See Also

[drop](/reference/agent/drop)