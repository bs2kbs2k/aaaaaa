# move

Request the agent to move in a certain direction.

```sig
agent.move(SixDirection.Forward, 1);
```

## Parameters

* **direction**: the direction to move the agent, such as: SixDirection.Forward
* **blocks**: how far the agent should move, in blocks, like: 1

## Example

Move your agent backwards by 3 blocks.

```blocks
agent.move(SixDirection.Back, 3);
```

## See Also

[`||agent:turn||`](/reference/agent/turn)