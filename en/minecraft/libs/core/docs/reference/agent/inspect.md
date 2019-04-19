# inspect

Inspects a block in the specified direction and returns the block ID or data.

```sig
agent.inspect(AgentInspection.Block, SixDirection.Forward);
```

## Parameters

* **kind**: the desired result type for the detection: block id or data
* **direction**: the direction in which to inspect, eg: SixDirection.Forward

## Example

The following inspects the block in front of the agent, and places the same block type above the player's head.

```blocks
blocks.place(agent.inspect(AgentInspection.Block, SixDirection.Forward), positions.create(0, 2, 0));
```