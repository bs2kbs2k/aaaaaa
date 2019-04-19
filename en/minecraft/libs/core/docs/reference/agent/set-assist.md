# set Assist

Control which assists are enabled for the agent. Assists are extra powers you give to the agent.

```sig
agent.setAssist(AgentAssist.PlaceOnMove, false);
```

## Parameters

* **assist**: the super power of the agent! > * `place on move`: the agent will place a block from its active inventory slot every time it moves > * `place from any slot`: if there are no blocks or items in the agent's active inventory slot, the agent will try to use other inventory slots > * `destroy obstacles`: if the agent can't move because of an obstacle, it will destroy the obstacle before moving
* **on**: set the assist to enabled or not enabled (`true` for enabled, `false` for not enabled)

## Example

Make the agent place a block when it moves, and then command it to move 3 blocks forward. If the agent has blocks in its active inventory slots, the agent will place them as it moves!

```blocks
agent.setAssist(AgentAssist.PlaceOnMove, true);
agent.move(SixDirection.Forward, 3);
```