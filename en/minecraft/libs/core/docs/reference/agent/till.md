# till

Commands the agent to till soil in the given direction.

```sig
agent.till(SixDirection.Forward);
```

## Parameters

* **direction**: the direction in which to till the soil, eg: SixDirection.Forward

## Example

Makes the agent till behind itself.

```blocks
agent.till(SixDirection.Back);
```