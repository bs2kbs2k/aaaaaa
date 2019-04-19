# detect

Detect if there is a block next to the agent in the specified direction.

```sig
agent.detect(AgentDetection.Block, SixDirection.Forward);
```

## Parameters

* **kind**: what the agent should attempt to detect > * `block`: detect any destructible block > * `redstone`: detect only redstone
* **direction**: the direction in which to perform the detection, such as: SixDirection.Forward

## Example

Display a message in the game chat if there is redstone in front of the agent.

```blocks
if (agent.detect(AgentDetection.Redstone, SixDirection.Forward)) {
    player.say("Agent found redstone!");
}
```