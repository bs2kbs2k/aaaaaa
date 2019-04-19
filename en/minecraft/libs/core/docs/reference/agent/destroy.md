# destroy

Commands the agent to destroy a block in the given direction.

```sig
agent.destroy(SixDirection.Forward);
```

## Parameters

* **direction**: the direction in which the agent will destroy a block, eg: SixDirection.Forward

## Example

If there's a block in front of the agent, the agent will destroy it.

```blocks
if (agent.detect(AgentDetection.Block, SixDirection.Forward)) {
    agent.destroy(SixDirection.Forward);
}
```